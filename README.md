// Colors
let africaColor = "#D4A2C1"; // Africa color
let europeColor = "#B0E0E6"; // Europe color
let textColor = "#000000"; // Black text

// Setup the initial canvas
function setup() {
  createCanvas(800, 600);  // Create canvas for the animation
  background(255);         // White background

  // Start the animation after a delay
  setTimeout(startBerlinConference, 2000);
}

// Draw Africa and Europe (maps are simplified)
function draw() {
  drawAfrica();  // Draw simplified map of Africa
  drawEurope();  // Draw simplified map of Europe
  displayTitle(); // Display title "The Scramble for Africa"
}

// Function to draw Africa map (simplified as an ellipse)
function drawAfrica() {
  fill(africaColor);
  noStroke();
  ellipse(300, 350, 200, 250);  // Africa's ellipse
}

// Function to draw Europe map (simplified as a circle)
function drawEurope() {
  fill(europeColor);
  ellipse(600, 150, 100, 100);  // Europe’s circle
}

// Display the title on the screen
function displayTitle() {
  fill(textColor);
  textSize(40);
  textAlign(CENTER);
  text("The Scramble for Africa", width / 2, 50);
}

// Start Berlin Conference animation
function startBerlinConference() {
  // Animation for European leaders gathering around the Africa map
  textSize(30);
  text("European Leaders are dividing Africa!", width / 2, height - 100);

  // Start a loop for the leaders' movements
  animateLeaders();
}

// Draw European Leaders (cartoonish style)
function animateLeaders() {
  fill(0, 102, 153);  // Germany (Bismarck)
  ellipse(500, 250, 50, 50);  // Leader 1 - Germany
  
  fill(0, 204, 255);  // France
  ellipse(650, 250, 50, 50);  // Leader 2 - France
  
  fill(255, 204, 0);  // Belgium (Leopold)
  ellipse(750, 250, 50, 50);  // Leader 3 - Belgium

  // Add leader movement for a sense of action
  let moveLeader = frameCount % 120;
  if (moveLeader < 60) {
    ellipse(500, 250 + moveLeader, 50, 50); // Bismarck moving
    ellipse(650, 250 + moveLeader, 50, 50); // France moving
    ellipse(750, 250 + moveLeader, 50, 50); // Leopold moving
  }
}

// Scene 2: Africa Before the Scramble
let scene = 1;  // Define scene
function mousePressed() {
  scene++;  // Move to the next scene when mouse is clicked
}

function draw() {
  if (scene === 1) {
    drawAfrica();
    drawEurope();
    displayTitle();
    startBerlinConference(); // Berlin Conference animation
  } else if (scene === 2) {
    drawAfricaBefore();
  }
}

// Scene 2: Africa Before Colonization
function drawAfricaBefore() {
  fill(0, 153, 0); // Green for rich land
  ellipse(300, 350, 200, 250);  // Representing Africa as rich in resources
  
  // Display message about Africa's richness before colonization
  fill(textColor);
  textSize(30);
  text("Africa, rich in culture and trade.", width / 2, height - 50);
}