# series
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Transmisión en Vivo M3U8</title>
  <style>
    body { margin: 0; padding: 20px; font-family: Arial; background-color: #f4f4f4; text-align: center; }
    h1 { color: #222; }
    video { 
      width: 100%; 
      max-width: 1200px; /* Video más grande */
      margin: 0 auto; 
      border-radius: 5px; 
    }
  </style>
</head>
<body>
  <h1>Transmisión en Vivo</h1>
  <video id="my-video" class="video-js" controls autoplay muted></video>
  <script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
  <script>
    var video = document.getElementById('my-video');
    var videoSrc = 'https://app.viloud.tv/hls/channel/8823313f19b20ef55dea4f3ad8a4cab7.m3u8'; 
    if (Hls.isSupported()) {
      var hls = new Hls();
      hls.loadSource(videoSrc);
      hls.attachMedia(video);
    } else if (video.canPlayType('application/vnd.apple.mpegurl')) {
      video.src = videoSrc;
