# Event-Handling-in-JavaScript


📘 README – Dynamic Profile Card Generator (JavaScript DOM)
📌 Project Description

This project creates dynamic profile cards using HTML, CSS, and JavaScript.
When a user fills the form and clicks Submit, a card is generated automatically without reloading the page.

Each card displays:

Profile Image

Name

Occupation

Short Info

🛠️ Technologies Used

HTML – Structure

CSS – Styling

JavaScript (DOM Manipulation) – Logic & Dynamic Content

📂 Project Structure
project-folder/
│
├── index.html
├── script.js
└── README.md

⚙️ How It Works (Overall Flow)

User fills the form

Form submission is stopped (page reload disabled)

JavaScript creates a card dynamically

Data from inputs is inserted into the card

Card is added to the page

Form inputs are cleared

🧠 Step-by-Step Code Explanation
1️⃣ Selecting Elements from DOM
let form = document.querySelector("form");
let inputs = document.querySelectorAll("input");
let main = document.querySelector("#main");

🔹 Explanation:

form → selects the <form>

inputs → selects all input fields

main → selects the container where cards will be added

2️⃣ Listening to Form Submit Event
form.addEventListener("submit", function (dets) {
    dets.preventDefault();

🔹 Explanation:

submit event triggers when user clicks submit

preventDefault() stops page reload
❗ Important for dynamic websites

3️⃣ Creating Card Structure
let card = document.createElement("div");
card.classList.add("card");

🔹 Explanation:

Creates a new <div>

Adds .card class for styling

4️⃣ Creating Profile Image Section
let profile = document.createElement("div");
profile.classList.add("profile");

let img = document.createElement("img");
img.setAttribute("src", inputs[0].value);

🔹 Explanation:

Creates profile container

Image src is taken from first input

User enters image URL

5️⃣ Creating Text Elements
let h3 = document.createElement("h3");
h3.textContent = inputs[1].value;

let h5 = document.createElement("h5");
h5.textContent = inputs[2].value;

let p = document.createElement("p");
p.textContent = inputs[3].value;

🔹 Explanation:

h3 → Name

h5 → Occupation

p → Info

Values are taken from form inputs

6️⃣ Appending Elements in Proper Order
profile.appendChild(img);
card.appendChild(profile);
card.appendChild(h3);
card.appendChild(h5);
card.appendChild(p);
main.appendChild(card);

🔹 Explanation:

HTML structure created dynamically:

<div class="card">
  <div class="profile">
    <img />
  </div>
  <h3>Name</h3>
  <h5>Occupation</h5>
  <p>Info</p>
</div>

7️⃣ Clearing Input Fields After Submit
inputs.forEach(function (inp) {
  if (inp.type !== "submit") {
    inp.value = "";
  }
});

🔹 Explanation:

Loops through all inputs

Clears text fields

Submit button value stays unchanged

🎨 CSS Highlights

.card → styled card layout

.profile → circular image

object-fit: cover → image fits properly

inline-block → cards appear side-by-side

🚀 Features

✔ No page reload
✔ Dynamic card creation
✔ Clean UI
✔ Beginner-friendly DOM manipulation

📌 Future Improvements (Optional)

Image validation

Delete card button

Edit card option

LocalStorage support

Responsive layout

✅ Conclusion

This project is a perfect example of DOM manipulation using JavaScript.
It teaches:

Event handling

Element creation

Dynamic UI updates

Form handling
