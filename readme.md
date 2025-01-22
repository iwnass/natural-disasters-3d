## To run the project follow the below guidelines:

# open the folder in VSC

# open terminal in the root folder

# npm init -y

# npm install three

# npm install d3-geo

# npm run dev

## READY!!!



// Animation loop
        function animate() {
            requestAnimationFrame(animate);

            // Rotate Earth
            earth.rotation.y += 0.001;

            // Rotate Moon around Earth
            moonGroup.rotation.y += 0.005;

            // Update controls and render
            TWEEN.update();
            controls.update();
            renderer.render(scene, camera);
        }

        animate();


 // Add Moon
        const moonGeometry = new THREE.SphereGeometry(1, 32, 32);
        const moonMaterial = new THREE.MeshPhongMaterial({ map: moonTexture });
        const moon = new THREE.Mesh(moonGeometry, moonMaterial);

        const moonOrbitRadius = 12; // Orbit radius around Earth
        const moonGroup = new THREE.Group();
        moon.position.set(moonOrbitRadius, 0, 0);
        moonGroup.add(moon);
        scene.add(moonGroup);