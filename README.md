# flores-amarillas
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flores Amarillas para Ti</title>
  <link rel="stylesheet" href="style.css">
  <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
</head>
<body>
  <div id="canvas-container"></div>
  <div class="mensaje-principal">
    <h1>Feliz Día de las Flores Amarillas 🌻</h1>
    <p>Toca la pantalla para interactuar</p>
  </div>
  <script src="script.js"></script>
</body>
</html>
body, html {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  background-color: #050505;
  font-family: 'Poppins', sans-serif;
}

#canvas-container {
  width: 100vw;
  height: 100vh;
  position: absolute;
  top: 0;
  left: 0;
}

.mensaje-principal {
  position: absolute;
  top: 10%;
  width: 100%;
  text-align: center;
  color: #fff2a3;
  text-shadow: 0 0 10px rgba(255, 215, 0, 0.8);
  pointer-events: none;
  z-index: 10;
}

h1 {
  font-size: 2rem;
  margin: 0;
}
// Configuración básica de Three.js
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer({ antialias: true });

renderer.setSize(window.innerWidth, window.innerHeight);
document.getElementById('canvas-container').appendChild(renderer.domElement);

// Crear partículas (estrellas/flores orbitando)
const geometry = new THREE.BufferGeometry();
const count = 500;
const positions = new Float32Array(count * 3);

for (let i = 0; i < count * 3; i += 3) {
  positions[i] = (Math.random() - 0.5) * 10;
  positions[i + 1] = (Math.random() - 0.5) * 10;
  positions[i + 2] = (Math.random() - 0.5) * 10;
}

geometry.setAttribute('position', new THREE.BufferAttribute(positions, 3));

const material = new THREE.PointsMaterial({
  color: 0xffd700, // Color amarillo girasol
  size: 0.05
});

const particles = new THREE.Points(geometry, material);
scene.add(particles);

camera.position.z = 5;

// Animación de rotación
function animate() {
  requestAnimationFrame(animate);
  particles.rotation.y += 0.002;
  renderer.render(scene, camera);
}
animate();
body, html {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  background-color: #050505;
  font-family: 'Poppins', sans-serif;
}

#canvas-container {
  width: 100vw;
  height: 100vh;
  position: absolute;
  top: 0;
  left: 0;
}

.mensaje-principal {
  position: absolute;
  top: 10%;
  width: 100%;
  text-align: center;
  color: #fff2a3;
  text-shadow: 0 0 10px rgba(255, 215, 0, 0.8);
  pointer-events: none;
  z-index: 10;
}

h1 {
  font-size: 2rem;
  margin: 0;
}
// Configuración básica de Three.js
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer({ antialias: true });

renderer.setSize(window.innerWidth, window.innerHeight);
document.getElementById('canvas-container').appendChild(renderer.domElement);

// Crear partículas (estrellas/flores orbitando)
const geometry = new THREE.BufferGeometry();
const count = 500;
const positions = new Float32Array(count * 3);

for (let i = 0; i < count * 3; i += 3) {
  positions[i] = (Math.random() - 0.5) * 10;
  positions[i + 1] = (Math.random() - 0.5) * 10;
  positions[i + 2] = (Math.random() - 0.5) * 10;
}

geometry.setAttribute('position', new THREE.BufferAttribute(positions, 3));

const material = new THREE.PointsMaterial({
  color: 0xffd700, // Color amarillo girasol
  size: 0.05
});

const particles = new THREE.Points(geometry, material);
scene.add(particles);

camera.position.z = 5;

// Animación de rotación
function animate() {
  requestAnimationFrame(animate);
  particles.rotation.y += 0.002;
  renderer.render(scene, camera);
}
animate();
