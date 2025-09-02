<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Многоножка</title>
  <style>
    body {
      margin: 0;
      overflow: hidden;
      background: black;
    }
    canvas {
      display: block;
    }
  </style>
</head>
<body>
  <canvas id="canvas"></canvas>

  <script>
    const canvas = document.getElementById("canvas");
    const ctx = canvas.getContext("2d");
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    // Следим за мышкой
    let mouse = { x: canvas.width / 2, y: canvas.height / 2 };
    window.addEventListener("mousemove", e => {
      mouse.x = e.clientX;
      mouse.y = e.clientY;
    });

    class Node {
      constructor(x, y, size) {
        this.x = x;
        this.y = y;
        this.size = size;
      }
    }

    class Centipede {
      constructor(length) {
        this.nodes = [];
        this.end = { x: mouse.x, y: mouse.y };
        this.speed = 10;

        for (let i = 0; i < length; i++) {
          this.nodes.push(new Node(mouse.x, mouse.y, 10));
        }
      }

      moveTo(x, y) {
        let dist = ((x - this.end.x) ** 2 + (y - this.end.y) ** 2) ** 0.5;
        let len = Math.max(0, dist - this.speed);

        for (let i = this.nodes.length - 1; i >= 0; i--) {
          let node = this.nodes[i];
          let ang = Math.atan2(node.y - y, node.x - x);
          node.x = x + len * Math.cos(ang);
          node.y = y + len * Math.sin(ang);
          x = node.x;
          y = node.y;
          len = node.size;
        }
      }

      update() {
        this.moveTo(mouse.x, mouse.y);
      }

      draw() {
        ctx.strokeStyle = "white";
        ctx.lineWidth = 2;

        ctx.beginPath();
        ctx.moveTo(this.nodes[0].x, this.nodes[0].y);
        for (let node of this.nodes) {
          ctx.lineTo(node.x, node.y);
        }
        ctx.stroke();

        // Рисуем лапки
        for (let i = 0; i < this.nodes.length; i += 3) {
          let node = this.nodes[i];
          let angle = Math.atan2(
            this.nodes[Math.min(i + 1, this.nodes.length - 1)].y - node.y,
            this.nodes[Math.min(i + 1, this.nodes.length - 1)].x - node.x
          );

          ctx.beginPath();
          ctx.moveTo(node.x, node.y);
          ctx.lineTo(node.x + 15 * Math.cos(angle + Math.PI / 2),
                     node.y + 15 * Math.sin(angle + Math.PI / 2));
          ctx.moveTo(node.x, node.y);
          ctx.lineTo(node.x + 15 * Math.cos(angle - Math.PI / 2),
                     node.y + 15 * Math.sin(angle - Math.PI / 2));
          ctx.stroke();
        }
      }
    }

    const centipede = new Centipede(50);

    function animate() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      centipede.update();
      centipede.draw();
      requestAnimationFrame(animate);
    }

    animate();
  </script>
</body>
</html>