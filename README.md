# Superb-tang
Volcano

![buh](https://github.com/nicolasbaez/Superb-tang/blob/main/xp025.gif)
```javascript
h = 255;
setup = (_) => createCanvas((w = 500), w, WEBGL);
draw = (_) => {
  clear();
  noFill();
  rotateX(1);
  rotateZ(w / 2);
  for (j = 1; j < 18; j += 0.25) {
    beginShape();
    stroke(j * 14, 0, h - j * 9);
    for (i = 0; i < 2 * PI; i += 0.05) {
      r = w / (j * 2);
      vertex(
        r * cos(i),
        r * sin(i),
        noise(i * 27, j * 27, w) * sin(j * 0.08) * h
      );
    }
    endShape();
  }
  w -= 0.04;
};

keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp025.gif", 418, { delay: 0, units: "frames" });
  }
};
