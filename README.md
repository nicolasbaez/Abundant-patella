# Abundant-patella
a beautiful snail dancing some chillout
```javascript
k = 0;
w = 500;
h = 250;
setup = (_) => {
  createCanvas(w, w, WEBGL);
  frameRate(5);
};
draw = (_) => {
  rotateX(k);
  clear();
  noFill();
  stroke(h, h * sin(k), h);
  for (i = 0; i < 3; i += 0.1) {
    beginShape();
    for (j = 0; j < 6; j += 0.1) {
      r = map(sin(i * j), 0, 1, h / 3, h / 4);
      vertex(r * sin(i) * cos(j), r * sin(i) * sin(j), r * cos(i));
    }
    endShape();
  }
  k += 0.05;
  if(k<=2*PI){
    save("pj5_001_"+frameCount+".png");
  }
};
