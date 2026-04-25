<!DOCTYPE html>
<html>
<head>
    <style>
        body { background: black; color: red; font-family: monospace; display: flex; align-items: center; justify-content: center; height: 100vh; overflow: hidden; }
        pre { font-size: 10px; line-height: 10px; }
    </style>
</head>
<body>
    <pre id="heart"></pre>
    <script>
        const el = document.getElementById('heart');
        let frame = 0;
        function draw() {
            let str = "";
            for (let y = 15; y > -15; y--) {
                for (let x = -30; x < 30; x++) {
                    let d = Math.pow(x*0.05, 2) + Math.pow(y*0.1, 2) - 1;
                    if (d*d*d - Math.pow(x*0.05, 2) * Math.pow(y*0.1, 3) <= 0) {
                        str += "I LOVE YOU "[(x + frame) % 11 || 0];
                    } else { str += " "; }
                }
                str += "\n";
            }
            el.innerText = str;
            frame++;
            setTimeout(draw, 100);
        }
        draw();
    </script>
</body>
</html>
