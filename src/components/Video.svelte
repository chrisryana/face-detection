
<script>
    import { onMount, onDestroy } from 'svelte';

    let status = 'loading';
    let video;
    let wrapper;
    let interval;

    const playListener = () => {
                const canvas = window.faceapi.createCanvasFromMedia(video);
                const displaySize = { width: video.width, height: video.height };
        
                wrapper.append(canvas);
                faceapi.matchDimensions(canvas, displaySize);
        
                interval = setInterval(async () => {
                    const detections = await window.faceapi.detectAllFaces(video, new window.faceapi.TinyFaceDetectorOptions())
                        .withFaceExpressions();
                    const resizedDetections = window.faceapi.resizeResults(detections, displaySize);
                    canvas.getContext('2d').clearRect(0, 0, canvas.width, canvas.height);
                    window.faceapi.draw.drawDetections(canvas, resizedDetections);
                    window.faceapi.draw.drawFaceExpressions(canvas, resizedDetections);
                    resizedDetections.forEach(({expressions}) => {
                        const sorted = expressions.asSortedArray();
                        console.log(sorted[0]);

                    });
        
                    status = 'success';
                }, 100);


                // return {
                //     destroy: ()=>{video.removeEventListener('play',playListener); clearInterval(interval);}
                // }
            }

    onMount(async () => {
        if (!window.faceapi) {
            status = 'error';
            return;
        };

        await window.faceapi.nets.tinyFaceDetector.loadFromUri('./weights');
        await window.faceapi.nets.faceRecognitionNet.loadFromUri('./weights');
        await window.faceapi.nets.faceExpressionNet.loadFromUri('./weights');
        // await window.faceapi.nets.ageGenderNet.loadFromUri('./weights');
    
        try {
            const stream = await navigator.mediaDevices.getUserMedia({
                video: { width: 312, height: 250 },
            });
            video.srcObject = stream;
            status = 'success';
        } catch(err) {
            console.error(err)
            status = 'error';
        }
    
        // video.addEventListener('play', playListener)
    })

    onDestroy(() => {
        video.removeEventListener('play', playListener)
        clearInterval(interval);
    })

</script>

<div class="wrapper" bind:this={wrapper}>
    {#if status === 'error'}
	    <div class="error">Для отображения контента разрешите доступ к камере</div>
    {/if}

    {#if status === 'loading'}
        <div class="loader">Распознаю твое личико (ಠ_ಠ)...</div>
    {/if}
	
	<video class="video" on:play={playListener} bind:this={video} id="video" width="312" height="250" autoplay muted></video>
</div>



<style>
    .wrapper {
		/* padding: 20px; */
		/* height: 100vh; */
		display: flex;
		align-items: center;
		justify-content: center;
        border-radius: 10px;
	}

	.error, .loader {
		padding: 8px 20px;
		text-align: center;
		border-radius: 3px;
	}

	.error {
		background-color: #ffe9e9;
		color: #ff7171;
		border: 1px solid #ff7171;
	}

	.loader {
		opacity: 0.6;
		position: absolute;
		background-color: #e9ffeb;
		color: #34dc51;
		border: 1px solid #34dc51;
	}

    .video {
        border-radius: 10px;
    }
</style>

