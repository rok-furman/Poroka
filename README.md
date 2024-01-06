<!DOCTYPE html>
<html>
<head>
	<title>Spletna stran z vgrajeno kamero in učinki</title>
	<style>
		#video {
			width: 640px;
			height: 480px;
			background-color: black;
		}
		#canvas {
			display: none;
		}
	</style>
</head>
<body>
	<h1>Spletna stran z vgrajeno kamero in učinki</h1>
	<video id="video"></video>
	<canvas id="canvas"></canvas>
	<script>
		const video = document.getElementById('video');
		const canvas = document.getElementById('canvas');
		const context = canvas.getContext('2d');

		navigator.mediaDevices.getUserMedia({ video: true })
			.then((stream) => {
				video.srcObject = stream;
				video.play();
			});

		video.addEventListener('play', () => {
			setInterval(() => {
				context.drawImage(video, 0, 0, 640, 480);
				const pixels = context.getImageData(0, 0, 640, 480);
				for (let i = 0; i < pixels.data.length; i += 4) {
					pixels.data[i + 0] = pixels.data[i + 0] + 100; // red
					pixels.data[i + 1] = pixels.data[i + 1] - 50; // green
					pixels.data[i + 2] = pixels.data[i + 2] * 0.5; // blue
				}
				context.putImageData(pixels, 0, 0);
			}, 16);
		});
	</script>
</body>
</html>
