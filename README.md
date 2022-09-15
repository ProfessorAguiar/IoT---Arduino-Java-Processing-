# IoT com Arduino e Java(Processing) em andamento...
### Projeto de automação com Arduino usando Interface gráfica em Java para controle e monitoramento. 
<img src="tela1.png"/>
#### Código:
import controlP5.*;

ControlP5 cp5;

int col = color(255);

boolean toggleValue = false;

PImage img;


void setup() {
  size(800,600);
  
  img = loadImage("planta.jpeg");
  img.resize(800, 600);
  background(img);
  

  
  smooth();
  cp5 = new ControlP5(this);
  // create a toggle and change the default look to a (on/off) switch look
  cp5.addToggle("Quarto")
     .setPosition(40,50)
     .setSize(100,20)
     .setValue(true)
     .setMode(ControlP5.SWITCH)
     ;
     
textSize(20);
fill(0, 200, 612);
text("Sala", 40, 40); 
fill(0, 200, 612);
text("Quarto", 40, 100);
fill(0, 200, 612, 204);
text("Cozinha", 40, 160);
     
}
  

void draw() {
  pushMatrix();
  translate(0,150);
  fill(col);
  popMatrix();
}
void toggle(boolean theFlag) {
  if(theFlag==true) {
    col = color(255);
  } else {
    col = color(100);
  }
  println("a toggle event.");
}
