Project Platform Technologies
Dino Showcase
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dinosaurs Showcase</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: left;
      background-image: url('https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExMmZsc2h5aDRzMzQ0OGRjM3ltOWJobnN1cDQ3Z3pid2I0Z3dwcnA2diZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/mjW8ytWgjLS1O/giphy.webp');
      background-size: auto;
      background-color: #000000;
      margin: 0;
      padding: 0;
    }
    .container {
      margin-left: 10px;  
      padding: 200px;
      background-color: #ffe4c4b9;
      border-radius: 10px;
      width: 300px;
      margin-left: auto;
      margin-right: auto;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      border: none;
      background-color: #e20938;
      color: white;
      border-radius: 5px; 
      cursor: pointer;
    }
    button:hover {
      background-color: #b84c51;
    }
    .dinosaur {
      margin-top: 50px;
      color: #333;
    }
    img {
      margin-bottom: 100px;
      max-width: 150%;
      border-radius: 50px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Dinosaurs Showcase</h1>
    <button onclick="generateDinosaur()">ROAR</button>
    <div class="dinosaur" id="dinosaurContainer">
      
    </div>
  </div>
  <script>
    
    const dinosaurs = [
      { name: "Tyrannosaurus Rex", img: "https://media.cnn.com/api/v1/images/stellar/prod/nm-tyrannosaur-sergey-krasovskiy-full.jpg?c=original" },
      { name: "Velociraptor", img: "https://dinosaurland.es/wp-content/uploads/2024/02/21-Velociraptor.jpeg" },
      { name: "Triceratops", img: "https://www.dinosaur.org/wp-content/uploads/2023/02/a-lone-Triceratops-drinks-from-a-crystal-clear-lake-at-dawn-1024x574.png" },
      { name: "Brachiosaurus", img: "https://a-z-animals.com/media/2022/05/Brachiosaurus.jpg" },
      { name: "Stegosaurus", img: "https://dinosaurland.es/wp-content/uploads/elementor/thumbs/02-Stegosaurus-qm41rsssrvucjnhzs27cnkxsajz3zomvf8vsbv3ri8.jpeg" },
      { name: "Spinosaurus", img: "https://dinosaurland.es/wp-content/uploads/2024/02/12-Spinosaurus.jpeg" },
      { name: "Ankylosaurus", img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTGnQHlW_7ufn3D-qI_nNao6Em-fPCpFm83jw&s" },
      { name: "Allosaurus", img: "https://dinosaurland.es/wp-content/uploads/2024/02/03-Allosaurus.jpg" },
      { name: "Iguanodon", img: "https://science-resources.co.uk/KS2/Dinosaurs/I/Iguanodon.jpg" },
      { name: "Pterodactyl", img: "https://i0.wp.com/onlydinosaurs.com/wp-content/uploads/2021/12/A-Pterodactyl-is-flying-across-the-mountain-with-a-fish-in-its-mouth.jpg" },
      { name: "Diplodocus", img: "https://easy-peasy.ai/cdn-cgi/image/quality=80,format=auto,width=700/https://fdczvxmwwjwpwbeeqcth.supabase.co/storage/v1/object/public/images/4de27af8-da46-4447-bcd7-694ec4baebfc/6dabd2a1-ae09-4da1-bb9a-8f21b31d9b6e.png" },
      { name: "Carnotaurus", img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQlaHLew7K_SK-79htzXpe7enW9m-Tq0Rx2PA&s" },
      { name: "Parasaurolophus", img: "https://static.wikia.nocookie.net/jurassicworld-evolution/images/c/cf/Jurassic_World_Evolution_Screenshot_2020.01.08_-_21.06.32.21.png/revision/latest/scale-to-width/360?cb=20200120120641" },
      { name: "Pachycephalosaurus", img: "https://images.fineartamerica.com/images/artworkimages/mediumlarge/2/pachycephalosaurus-dinosaur-roger-harrisscience-photo-library.jpg" },
      { name: "Gigantosaurus", img: "https://t4.ftcdn.net/jpg/05/98/17/03/360_F_598170393_oInuUEjW5mcTld1SkJIL99V0YVANSxjr.jpg" },
      { name: "Therizinosaurus", img: "https://static1.srcdn.com/wordpress/wp-content/uploads/2022/08/Therizinosaurus-in-Jurassic-World-Dominion.jpg" },
      { name: "Coelophysis", img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRxR20nnW53lt5vEPsvLr75Kny37J1uxng4Lg&s" },
      { name: "Microraptor", img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSADJdUu5APj16JgjHeeXfD05k75Kf_bAHhTg&s" },
      { name: "Mosasaurus", img: "https://scitechdaily.com/images/Mosasaurus-Concept.jpg" },
      { name: "Compsognathus", img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRtu-xyRZZi1YGf0-AnQBQ5A_FiWVHBFjiicQ&s" }
    ];

  
    function generateDinosaur() {
      const randomIndex = Math.floor(Math.random() * dinosaurs.length);
      const randomDinosaur = dinosaurs[randomIndex];

    
      const dinosaurContainer = document.getElementById('dinosaurContainer');
      dinosaurContainer.innerHTML = ''; 

 
      const dinosaurName = document.createElement('p');
      dinosaurName.textContent = randomDinosaur.name;

      
      const dinosaurImage = document.createElement('img');
      dinosaurImage.src = randomDinosaur.img;
      dinosaurImage.alt = randomDinosaur.name;

      
      dinosaurContainer.appendChild(dinosaurName);
      dinosaurContainer.appendChild(dinosaurImage);
    }
  </script>
</body>
</html>
