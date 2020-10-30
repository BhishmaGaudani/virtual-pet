# virtual-pet 
//Create variables here
var dog , happyDog, database, foodS, foodStock
function preload()
{
  dog.Image =  loadImage("dogimg.png")
  happyDog.Image = loadImage ("dogimg1.png")
	//load images here
}

function setup() {
	createCanvas(500, 500);
  foodStock=database.ref('food')
  foodStock.on(  " value ",readstock)

  if(keywentdown(UP_ARROW)){
    writestock(foodS);
    dog.addimage(happyDog)
  }
}
function readstock(data){
foods = data.val();

}
function writestock(x){
  database.ref('/').update({
    food:x
  });
  
  }

function draw() {  

  drawSprites();
  //add styles here

}



