# openCV-js
This contains compiled javascript version of OpenCV with default CMAKE flags

The steps taken were as instructed on [this repo](https://github.com/opencv/opencv/tree/master/platforms/js) 

## To see the working ,follow the steps

```
git clone https://github.com/shkrwnd/openCV-js.git
```
```
cd openCV-js
```
Just open index.html in any supported browser 
If first line of web-page shows ```OpenCV.js is ready``` that means it is working properly.
Then just choose any image and it will show that image in new canvas <dir> block.
###index.html



```<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Hello OpenCV.js</title>
</head>
<body>
<h2>Hello OpenCV.js</h2>
<p id="status">OpenCV.js is loading...</p>
<div>
  <div class="inputoutput">
    <img id="imageSrc" alt="No Image" />
    <div class="caption">imageSrc <input type="file" id="fileInput" name="file" /></div>
  </div>
  <div class="inputoutput">
    <canvas id="canvasOutput" ></canvas>
    <div class="caption">canvasOutput</div>
  </div>
</div>
<script type="text/javascript">
let imgElement = document.getElementById('imageSrc');
let inputElement = document.getElementById('fileInput');
inputElement.addEventListener('change', (e) => {
  imgElement.src = URL.createObjectURL(e.target.files[0]);
}, false);
imgElement.onload = function() {
  let mat = cv.imread(imgElement);
  cv.imshow('canvasOutput', mat);
  mat.delete();
};
function onOpenCvReady() {
  document.getElementById('status').innerHTML = 'OpenCV.js is ready.';
}
</script>
<script async src="opencv.js" onload="onOpenCvReady();" type="text/javascript"></script>
</body>
</html>```


