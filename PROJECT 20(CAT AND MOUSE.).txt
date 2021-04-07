var bgImg;
var cat, mouse;
var catImg1, mouseImg1;
var catImg2, mouseImg2;
var catImg3, mouseImg3;

function preload() {
    //load the images here
    bgImg = loadImage("garden.png");
    catImg1=  loadAnimation("images/cat4.png");
    mouseImg1=  loadAnimation("images/mouse4.png");
    catImg=  loadAnimation("cat2.png, cat3.png");
    mouseImg2=  loadAnimation("mouse2.png, mouse3.png");
    catImg3=  loadAnimation("images/cat1.png");
    mouseImg3=  loadAnimation("images/mouse1.png");
}

function setup(){
    createCanvas(1000,800);
    //create tom and jerry sprites here
        cat= createCanvas(200, 600,10, 10);
        cat.addImage('cat', catImg1);
        mouse=createSprite(800, 600, 10, 10)
        mouse.addImage('mouse', mouseImg1);
}

function draw() {

    background(255);
    //Write condition here to evalute if tom and jerry collide
     if(cat.x-mouse.x<(cat.width-mouse.width)/2){
      cat.changeAnimation("catHappy", catImg3);
      mouse.changeAnimation("mouseHappy", mouseImg3);
      cat.velocityX=0;
     }
    
    keyPressed();

    drawSprites();
}


function keyPressed(){

  //For moving and changing animation write code here

     if(keyCode===RIGHT_ARROW){
         mouse.addAnimation("mouseTeasing", mouseImg2);
         mouse.changeAnimation("mouseTeasing");
         mouse.frameDelay=25;
     }
     
    if(keyCode===LEFT_ARROW){
        mouse.addAnimation("mouseTeasing", mouseImg2);
        mouse.changeAnimation("mouseTeasing");
        mouse.frameDelay=25;
        cat.addAnimation('catRunning', catImg2);
        cat.changeAnimation('catRunning');
        cat.velocityX=-3;
    }
}
