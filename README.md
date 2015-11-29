# visualizaci-n-de-datos-2D

// visualizacion 2D

//variables
Table tB;
float VR1;
float VR2;
float VR3;
float VR4;
float VR5;
float VR6;
float VR7;
float VR8;
float VR10;
float VR11;
float VR12;
float VR13;
float VR14;
float VR15;
float VR16;
float VR17;
float VR20;
float VR21;
float VR22;
float VR23;
float VR24;
float VR25;
float VR26;
float VR27;

//full color
color c1 = color(65, 63, 232);
color c2 = color(37, 212, 226);
color c3 = color(170, 9, 232);
color c4 = color(232, 0, 216);
color c5 = color(232, 4, 11);
color c6 = color(232, 165, 18);
color c7 = color(232, 224, 5); 
color c8 = color(11, 232, 60);

//transparencia VI
color c10 = color(65, 63, 212, 100);
color c20 = color(37, 212, 226, 100);
color c30 = color(170, 9, 212, 100);
color c40 = color(212, 0, 216, 100);
color c50 = color(212, 4, 11, 100);
color c60 = color(212, 165, 18, 100);
color c70 = color(212, 224, 5, 100); 
color c80 = color(11, 212, 60, 100);

color x = color(0);

//tipos de letras
PFont fontR;
PFont fontR2;
PFont fontUL;
PFont fontUL2;
PFont fontUL3;
PFont fontA;

boolean isGreenOn = false;
boolean isYellowOn = false;
boolean isMustardOn = false;
boolean isRedOn = false;
boolean isPinkOn = false;
boolean isPurpleOn = false;
boolean isBlueOn = false;
boolean isLightBlueOn = false;

boolean isYearTwoOn = false;
boolean isYearThreeOn = false;
boolean isYearFourOn = false;

void setup() {
  size(1400, 1000);
  tB= loadTable ("tabla 6.4.csv", "header");
  // tipos de letras
  fontR= loadFont("TsukuARdGothic-Bold-32.vlw");
  textFont(fontR,32);
  smooth(4);
  
  fontR2= loadFont("TsukuARdGothic-Regular-32.vlw");
  textFont(fontR2,32);
  smooth(4);
  
  fontUL= loadFont("AvenirNext-UltraLight-32.vlw");
  textFont(fontUL,32);
  smooth(4);
  
  fontUL2= loadFont("AvenirNext-UltraLight-90.vlw");
  textFont(fontUL,90);
  smooth(3);
  
  fontUL3= loadFont("AvenirNext-UltraLight-18.vlw");
  textFont(fontUL,18);
  smooth(4);  
  
  fontA= loadFont("ArialHebrew-Bold-180.vlw");
  textFont(fontUL,180);
  smooth(4);
  
}


void draw() {
  //fondo
  background(255);

  
//variables radianes MAP
//nombre de variable=map(valor en %, 0,100,0,2*PI);
//EDITS IV
 VR1=map((tB.getInt(0, 6)), 0, 100, 0, 2*PI);
 VR2=map((tB.getInt(1, 6)), 0, 100, 0, 2*PI);
 VR3=map((tB.getInt(2, 6)), 0, 100, 0, 2*PI);
 VR4=map((tB.getInt(3, 6)), 0, 100, 0, 2*PI);
 VR5=map((tB.getInt(4, 6)), 0, 100, 0, 2*PI);
 VR6=map((tB.getInt(5, 6)), 0, 100, 0, 2*PI);
 VR7=map((tB.getInt(6, 6)), 0, 100, 0, 2*PI);
 VR8=map((tB.getInt(7, 6)), 0, 100, 0, 2*PI);
 //EDITS III
 VR10=map((tB.getInt(0, 5)), 0, 100, 0, 2*PI);
 VR11=map((tB.getInt(1, 5)), 0, 100, 0, 2*PI);
 VR12=map((tB.getInt(2, 5)), 0, 100, 0, 2*PI);
 VR13=map((tB.getInt(3, 5)), 0, 100, 0, 2*PI);
 VR14=map((tB.getInt(4, 5)), 0, 100, 0, 2*PI);
 VR15=map((tB.getInt(5, 5)), 0, 100, 0, 2*PI);
 VR16=map((tB.getInt(6, 5)), 0, 100, 0, 2*PI);
 VR17=map((tB.getInt(7, 5)), 0, 100, 0, 2*PI);
 //EDITS II
 VR20=map((tB.getInt(0, 4)), 0, 100, 0, 2*PI);
 VR21=map((tB.getInt(1, 4)), 0, 100, 0, 2*PI);
 VR22=map((tB.getInt(2, 4)), 0, 100, 0, 2*PI);
 VR23=map((tB.getInt(3, 4)), 0, 100, 0, 2*PI);
 VR24=map((tB.getInt(4, 4)), 0, 100, 0, 2*PI);
 VR25=map((tB.getInt(5, 4)), 0, 100, 0, 2*PI);
 VR26=map((tB.getInt(6, 4)), 0, 100, 0, 2*PI);
 VR27=map((tB.getInt(7, 4)), 0, 100, 0, 2*PI);
  
 
 titulo(); //linea 150
 anos(); //linea157
 convencionesColores(); //linea164
 pieChartIV(); //linea259
 pieChartIII();
 pieChartII();
 EDITS(); //linea 224
 circuloCentral(); // linea 244
 porcentaje();

// //texto de coordenadas
// text(mouseX + " , "+ mouseY, mouseX, mouseY);
  
}

void porcentaje() {
  rect(1030, 200, 300, 200);
  textFont(fontUL);
  fill(255);
  text("EDITSII:",1050,250);
  text("EDITSIII:",1050,310);
  text("EDITSIV:",1050,370);
}

void titulo() {
  fill(0);
  textFont(fontR);
  text("Distribución de la inversión según grupos de", 705, 60);
  text("actividades conducentes a la innovación.", 765, 100);
}

void anos() {
  fill(150);
  textFont(fontUL2);
  text("2008", 30, 95);
  text("2013", 40, 195);
}


void convencionesColores() {
  //texto
  fill(0);
  textFont(fontUL);
  text("Convenciones", 1030, 530);
  
  //rect(x, y, width, height)
  strokeWeight (2);
  stroke(255);
  fill(c8);
  rect(1035, 560, 25, 25);
  fill(0);
  textFont(fontUL3);
  //text("1%",1070, 580);
  text("Maquinaria y Equipo", 1070, 580);

  fill(c7);
  rect(1035, 615, 25, 25);
  fill(0);
  //text("1%",1070, 635);
  text("Investigación y Desarrollo", 1070, 635);

  fill(c6);
  rect(1035, 670, 25, 25);
  fill(0);
  //text("1%",1070, 690);  
  text("Asistencia Técnica y Consultoría", 1070, 690); 

  fill(c5);
  rect(1035, 725, 25, 25);
  fill(0);
  //text("1%",1070, 745); 
  text("Mercadeo de Innovaciones", 1070, 745);

  fill(c4);
  rect(1035, 780, 25, 25);
  fill(0);
  //text("1%",1070, 800);
  text("Transferencia de Tecnología", 1070, 800);

  fill(c3);
  rect(1035, 835, 25, 25);
  fill(0);
  //text("1%",1070, 855);
  text("Tecnologías de Información y", 1070, 855);
  text("Comunicaciones", 1070, 875);

  fill(c1);
  rect(1035, 890, 25, 25);
  fill(0);
  //text("1%",1070, 910); 
  text("Ingeniería y Diseño Industrial", 1070, 910);

  fill(c2);
  rect(1035, 945, 25, 25);
  fill(0);
  //text("1%",1070, 965);  
  text("Formación y Capacitación", 1070, 965);
}

void EDITS(){
  fill(0);
  textFont(fontUL3);
  text("Circulo central: total",20,870);
  
  strokeWeight(2);
  
  fill(0);
  ellipseMode(CENTER);
  ellipse(30, 893,20,20);
  text("EDITSII: 2008-2009",50,900);
  
  fill(0);
  ellipse(30, 923,20,20);
  text("EDITSIII: 2010-2011",50,930);
  
  fill(0);
  ellipse(30, 953,20,20);
  text("EDITSIV: 2012-2013",50,960);
}

void circuloCentral(){
  strokeWeight(2);
  stroke(255);
  textFont(fontR);
  //como llenar una figura de color
  fill(255);
  // x,y,ancho, alto
  ellipse(520, (height/2)+50, 212, 212); 
  fill(0);
  text(tB.getString(9,1),445,563);
  textFont(fontR2);
  text("$",430,563);
  println(tB.getString(9,1));
}

void pieChartIV(){
  //EDITS IV datos
  
  //translucido a full tono 
  
  
//formacion y capacitacion
if (isLightBlueOn == true || isYearFourOn == true) {
    fill(x);
  } else {
    fill(c2);
  }
   arc(520,(height/2)+50,850,850,VR1+VR2+VR3+VR4+VR5+VR6+VR7,VR1+VR2+VR3+VR4+VR5+VR6+VR7+VR8, PIE);
 
      
//ingenieria y diseño industrial
if (isBlueOn == true || isYearFourOn == true) {
    fill(x);
 } else {
   fill(c1);
 }
 arc(520, (height/2)+50, 850, 850, VR1+VR2+VR3+VR4+VR5+VR6, VR1+VR2+VR3+VR4+VR5+VR6+VR7, PIE);
  
//tecnologia de informacion y comunucaciones
  if (isPurpleOn == true || isYearFourOn == true) {
    fill(x);
  } else {
    fill(c3);
  }
  arc(520, (height/2)+50, 850, 850, VR1+VR2+VR3+VR4+VR5, VR1+VR2+VR3+VR4+VR5+VR6, PIE);
  
//transferencia de tecnologia
  if (isPinkOn == true || isYearFourOn == true) {
    fill(x);
  } else {
    fill(c4);
  }
  arc(520,(height/2)+50,850,850,VR1+VR2+VR3+VR4,VR1+VR2+VR3+VR4+VR5, PIE); 
  
//mercadeo de innovacion
  if (isRedOn == true || isYearFourOn == true) {
    fill(x);
  } else {
    fill(c5);
  }
  arc(520,(height/2)+50,850,850,VR1+VR2+VR3,VR1+VR2+VR3+VR4, PIE);
  
//asistencia tecnica
  if (isMustardOn == true || isYearFourOn == true) {
    fill(x);
  } else {
    fill(c6);
  }
  arc(520,(height/2)+50,850,850,VR1+VR2,VR1+VR2+VR3, PIE);
  
//investigacion y desarrollo
  if (isYellowOn == true || isYearFourOn == true) {
    fill(x);
  } else {
    fill(c7);
  }
  arc(520, (height/2)+50, 850, 850, VR1, VR1+VR2, PIE); 
  
//maquinria y equipo
  if (isGreenOn == true || isYearFourOn == true) {
    fill(x);
  } else {
    fill(c8);
  }
  arc(520, (height/2)+50, 850, 850, 0, VR1, PIE);
  
}

void pieChartIII(){
  //EDITS III datos
  
  //translucido a full tono 
  
  
//formacion y capacitacion
if (isLightBlueOn == true || isYearThreeOn == true) {
    fill(x);
   } else {
    fill(c2);
  }
    arc(520, (height/2)+50, 636, 636, VR10+VR11+VR12+VR13+VR14+VR15+VR16, VR10+VR11+VR12+VR13+VR14+VR15+VR16+VR17, PIE);
 
      
//ingenieria y diseño industrial
if (isBlueOn == true || isYearThreeOn == true) {
    fill(x);
  } else {
   fill(c1);
 }
    arc(520, (height/2)+50, 636, 636, VR10+VR11+VR12+VR13+VR14+VR15, VR10+VR11+VR12+VR13+VR14+VR15+VR16, PIE);
  
//tecnologia de informacion y comunucaciones
  if (isPurpleOn == true || isYearThreeOn == true) {
    fill(x);
   } else {
    fill(c3);
  }
    arc(520, (height/2)+50, 636, 636, VR10+VR11+VR12+VR13+VR14, VR10+VR11+VR12+VR13+VR14+VR15, PIE);
  
//transferencia de tecnologia
  if (isPinkOn == true || isYearThreeOn == true) {
    fill(x);
   } else {
    fill(c4);
  }
    arc(520, (height/2)+50, 636, 636, VR10+VR11+VR12+VR13, VR10+VR11+VR12+VR13+VR14, PIE); 
  
//mercadeo de innovacion
  if (isRedOn == true || isYearThreeOn == true) {
    fill(x);
   } else {
    fill(c5);
  }
    arc(520, (height/2)+50, 636, 636, VR10+VR11+VR12, VR10+VR11+VR12+VR13, PIE);  
  
//asistencia tecnica
  if (isMustardOn == true || isYearThreeOn == true) {
    fill(x);
   } else {
    fill(c6);
  }
    arc(520, (height/2)+50, 636, 636, VR10+VR11, VR10+VR11+VR12, PIE);
  
//investigacion y desarrollo
  if (isYellowOn == true || isYearThreeOn == true) {
    fill(x);
   } else {
    fill(c7);
  }
    arc(520, (height/2)+50, 636, 636, VR10, VR10+VR11, PIE);
  
//maquinria y equipo
  if (isGreenOn == true || isYearThreeOn == true) {
    fill(x);
   } else {
    fill(c8);
  }
    arc(520, (height/2)+50, 636, 636, 0, VR10, PIE);
  
}

void pieChartII(){
  //EDITS II datos
  
  //translucido a full tono 
  
  
//formacion y capacitacion
if (isLightBlueOn == true || isYearTwoOn == true) {
    fill(x);
   } else {
    fill(c2);
  }
   arc(520,(height/2)+50,424,424,VR20+VR21+VR22+VR23+VR24+VR25+VR26,VR20+VR21+VR22+VR23+VR24+VR25+VR26+VR27, PIE);

      
//ingenieria y diseño industrial
if (isBlueOn == true || isYearTwoOn == true) {
    fill(x);
  } else {
   fill(c1);
 }
  arc(520,(height/2)+50,424,424,VR20+VR21+VR22+VR23+VR24+VR25,VR20+VR21+VR22+VR23+VR24+VR25+VR26, PIE);
  
//tecnologia de informacion y comunucaciones
  if (isPurpleOn == true || isYearTwoOn == true) {
    fill(x);
   } else {
    fill(c3);
  }
  arc(520,(height/2)+50,424,424,VR20+VR21+VR22+VR23+VR24,VR20+VR21+VR22+VR23+VR24+VR25, PIE);
  
//transferencia de tecnologia
  if (isPinkOn == true || isYearTwoOn == true) {
    fill(x);
   } else {
    fill(c4);
  }
  arc(520,(height/2)+50,424,424,VR20+VR21+VR22+VR23,VR20+VR21+VR22+VR23+VR24, PIE); 
  
//mercadeo de innovacion
  if (isRedOn == true || isYearTwoOn == true) {
    fill(x);
  } else {
    fill(c5);
  }
  arc(520,(height/2)+50,424,424,VR20+VR21+VR22,VR20+VR21+VR22+VR23, PIE);  
  
//asistencia tecnica
  if (isMustardOn == true || isYearTwoOn == true) {
    fill(x);
  } else {
    fill(c6);
  }
  arc(520,(height/2)+50,424,424,VR20+VR21,VR20+VR21+VR22, PIE);
  
//investigacion y desarrollo
  if (isYellowOn == true || isYearTwoOn == true) {
    fill(x);
  } else {
    fill(c7);
  }
  arc(520, (height/2)+50, 424, 424, VR20, VR20+VR21, PIE);
  
//maquinria y equipo
  if (isGreenOn == true || isYearTwoOn == true) {
    fill(x);
  } else {
    fill(c8);
  }
  arc(520, (height/2)+50, 424, 424, 0, VR20, PIE); 
  
}



void mouseMoved() {
  
//convenciones

//maquinaria y equipo, verde
  if (mouseX > 1035 && mouseX < 1060 && mouseY > 560 && mouseY < 560+25) {
     isGreenOn = true; 
     textFont(fontR);
     fill (255);
     //II=37
     text(tB.getInt (0, 4), 1160, 250);
     text ("%", 1200,250);
     //III=34
     text(tB.getInt (0, 5), 1170, 310);
     text ("%", 1210,310);
     //IV=21
     text(tB.getInt (0, 6), 1175, 370);
     text ("%", 1215,370);
          
  } else {
     isGreenOn = false; 
  }
  
//investigacion y desarrollo, amarillo
  if (mouseX > 1035 && mouseX < 1060 && mouseY > 615 && mouseY < 615+25) {
  //if (mouseX > 1035 && mouseX < 1060 && mouseY > 560-25 && mouseY < 560) {
     isYellowOn = true; 
     textFont(fontR);
     fill (255);
     //II=
     text(tB.getInt (1, 4), 1160, 250);
     text ("%", 1200,250);
     //III=
     text(tB.getInt (1, 5), 1170, 310);
     text ("%", 1210,310);
     //IV=
     text(tB.getInt (1, 6), 1175, 370);
     text ("%", 1215,370);
  } else {
     isYellowOn = false; 
  }

//asistencia tecnica y consultoria, mostaza
  if (mouseX > 1035 && mouseX < 1060 && mouseY > 670 && mouseY < 670+25) {
     isMustardOn = true; 
     textFont(fontR);
     fill (255);
     //II=
     text(tB.getInt (2, 4), 1160, 250);
     text ("%", 1190,250);
     //III=
     text(tB.getInt (2, 5), 1170, 310);
     text ("%", 1200,310);
     //IV=
     text(tB.getInt (2, 6), 1175, 370);
     text ("%", 1205,370);
  } else {
     isMustardOn = false; 
  }

//mercadeo de innovaciones, rojo
  if (mouseX > 1035 && mouseX < 1060 && mouseY > 725 && mouseY < 725+25) {
     isRedOn = true; 
     textFont(fontR);
     fill (255);
     //II=
     text(tB.getInt (3, 4), 1160, 250);
     text ("%", 1200,250);
     //III=
     text(tB.getInt (3, 5), 1170, 310);
     text ("%", 1200,310);
     //IV=
     text(tB.getInt (3, 6), 1175, 370);
     text ("%", 1205,370);
  } else {
     isRedOn = false; 
  }

//transferencia de tecnologia, rosado
  if (mouseX > 1035 && mouseX < 1060 && mouseY > 780 && mouseY < 780+25) {
     isPinkOn = true;
     textFont(fontR);
     fill (255);
     //II=
     text(tB.getInt (4, 4), 1160, 250);
     text ("%", 1190,250);
     //III=
     text(tB.getInt (4, 5), 1170, 310);
     text ("%", 1200,310);
     //IV=
     text(tB.getInt (4, 6), 1175, 370);
     text ("%", 1205,370); 
  } else {
     isPinkOn = false; 
  }
  
//recnologias de informacion y comunicaciones, morado
  if (mouseX > 1035 && mouseX < 1060 && mouseY > 835 && mouseY < 835+25) {
     isPurpleOn = true; 
     textFont(fontR);
     fill (255);
     //II=
     text(tB.getInt (5, 4), 1160, 250);
     text ("%", 1200,250);
     //III=
     text(tB.getInt (5, 5), 1170, 310);
     text ("%", 1210,310);
     //IV=
     text(tB.getInt (5, 6), 1175, 370);
     text ("%", 1215,370);
  } else {
     isPurpleOn = false; 
  }
  
//ingenieria y diseño industrial, azul
  if (mouseX > 1035 && mouseX < 1060 && mouseY > 890 && mouseY < 890+25) {
     isBlueOn = true; 
          textFont(fontR);
     fill (255);
     //II=
     text(tB.getInt (6, 4), 1160, 250);
     text ("%", 1190,250);
     //III=
     text(tB.getInt (6, 5), 1170, 310);
     text ("%", 1200,310);
     //IV=
     text(tB.getInt (6, 6), 1175, 370);
     text ("%", 1205,370);
  } else {
     isBlueOn = false; 
  }  
  
//formacion y capacitacion, azul claro
  if (mouseX > 1035 && mouseX < 1060 && mouseY > 945 && mouseY < 945+25) {
     isLightBlueOn = true; 
     textFont(fontR);
     fill (255);
     //II=
     text(tB.getInt (7, 4), 1160, 250);
     text ("%", 1190,250);
     //III=
     text(tB.getInt (7, 5), 1170, 310);
     text ("%", 1200,310);
     //IV=
     text(tB.getInt (7, 6), 1175, 370);
     text ("%", 1205,370);
  } else {
     isLightBlueOn = false; 
  }  
  
//EDITS IV  
  if (mouseX > 20 && mouseX < 40 && mouseY > 943 && mouseY < 963) {
     isYearFourOn = true; 
  } else {
     isYearFourOn = false; 
  }

//EDITS III  
  if (mouseX > 20 && mouseX < 40 && mouseY > 913 && mouseY < 933) {
     isYearThreeOn = true; 
  } else {
     isYearThreeOn = false; 
  }
//EDITS II  
  if (mouseX > 20 && mouseX < 40 && mouseY > 883 && mouseY < 903) {
     isYearTwoOn = true; 
  } else {
     isYearTwoOn = false; 
  }
}
