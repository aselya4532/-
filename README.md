# -<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>VR: Юпитер и Солнечная система</title>
    <script src="https://aframe.io/releases/1.4.2/aframe.min.js"></script>
  </head>
  <body>
    <a-scene background="color: black">
      <!-- Камера -->
      <a-entity position="0 1.6 4">
        <a-camera>
          <a-cursor color="yellow"></a-cursor>
        </a-camera>
      </a-entity>

      <!-- Солнце -->
      <a-sphere position="0 0 -5" radius="1.5" color="orange"></a-sphere>

      <!-- Юпитер -->
      <a-sphere id="jupiter"
                position="2 1 -6"
                radius="1"
                src="https://upload.wikimedia.org/wikipedia/commons/e/e1/Jupiter_%28transparent%29.png"
                animation="property: rotation; to: 0 360 0; loop: true; dur: 8000">
      </a-sphere>

      <!-- Текст с информацией о Юпитере -->
      <a-text id="jupiter-info"
              value="Юпитер - самая большая планета Солнечной системы."
              position="1 2 -6"
              color="white"
              align="center"
              width="2"
              visible="false">
      </a-text>

      <!-- Другие планеты (пример) -->
      <a-sphere position="-2 0 -7" radius="0.4" color="blue"></a-sphere>  <!-- Земля -->
      <a-sphere position="-3 1 -7" radius="0.3" color="red"></a-sphere>  <!-- Марс -->

      <!-- Слушатель кликов на Юпитер -->
      <script>
        document.querySelector("#jupiter").addEventListener("click", function () {
          let info = document.querySelector("#jupiter-info");
          info.setAttribute("visible", !info.getAttribute("visible"));
        });
      </script>

    </a-scene>
  </body>
</html>
