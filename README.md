<!DOCTYPE html>
<html lang="en" >
<head>
  <meta charset="UTF-8">
  <title>CodePen - Image Mask Reveal Animation</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/normalize/5.0.0/normalize.min.css">
  <link rel="stylesheet" href="./style.css">
  <style>
    body {
  height: 2000px;
}

h1 {
  position: fixed;
  top: 50%;
  left: 50%;
  font-family: sans-serif;
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-size: 12px;
  transform: translate(-50%, -50%);
}
h1 svg {
  width: 14px;
  display: block;
  margin: 10px auto;
}
h1 svg .arrow {
  -webkit-animation: scroll 0.35s ease-in alternate infinite;
          animation: scroll 0.35s ease-in alternate infinite;
}

@-webkit-keyframes scroll {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(10px);
  }
}

@keyframes scroll {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(10px);
  }
}
#cover {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url("https://images.unsplash.com/45/Ss2c5MVASdGkVHOwG6n9_Imogene%20Pass.jpg?dpr=1&auto=format&fit=crop&w=1500&h=997&q=80&cs=tinysrgb&crop=");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  -webkit-mask: url("http://www.supah.it/dribbble/video-clip-mask.png?v=1");
          mask: url("http://www.supah.it/dribbble/video-clip-mask.png?v=1");
  -webkit-mask-size: 1800% 100%;
          mask-size: 1800% 100%;
}
  </style>
    
</head>
<body>
<h1>
  scroll
  <svg version="1.1" id="svg-arrow-down" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 22 35" style="enable-background:new 0 0 22 35;" xml:space="preserve">
    <polygon class="arrow" style="fill:#000000;" points="20.58,11.584 12.004,20.158 12.004,0 9.996,0 9.996,20.158 1.42,11.584 0,13.004 11,24
					22,13.004 "></polygon>
  </svg></h1>
<div id="cover"></div>
<!-- partial -->
  <script src='https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js'>
    $(window).scroll(function(e) {
  frames = 17;
  step = ($("body").height() - $(window).height()) / frames;
  scrollStep = parseInt($(window).scrollTop() / step);
  maskPosition = 100 / frames * scrollStep;
  $("#cover").css({
    "mask-position": maskPosition + "% 50%",
    "-webkit-mask-position": maskPosition + "% 50%"
  });
});

/* Just for CodePen Thumbnail */
$("html, body").animate({ scrollTop: $(document).height() - $(window).height() }, 1200).queue(function(next) {
  $("html, body").animate({ scrollTop: 0 }, 1200);
  next();
});
  </script><script  src="./script.js"></script>
    
</body>
</html>
