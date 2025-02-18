<template>
  <main>
    <section class="hero" id="HOMERUN">
      <div class="hero-content">
        <div class="hero-text">
          <h1>Bienvenido a mi Portfolio</h1>
          <h2>Desarrollador Web & Diseñador UX/UI</h2>
        </div>
      </div>
    </section>

    <section class="about" id="ABOUTME">
      <div class="about-content">
        <img :src="profileImage" alt="Your Name" class="profile-image">
        <div class="about-text">
          <h2 class="aabout">Sobre mí</h2>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam quidem alias ipsa aperiam esse, unde atque, dolorum vero, adipisci voluptatibus consectetur.
          </p>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Vel, saepe corrupti suscipit quisquam ipsum provident fuga cupiditate voluptas maiores iure beatae repudiandae id quibusdam quam iste impedit. Obcaecati, blanditiis incidunt?
          </p>
        </div>
      </div>
    </section>

    <!--6 IMAGENES-->
    <section id="GALERIAP">
      <div class="container" id="GALERIAP">
        <h2 class="title">Galería de Proyectos</h2>
        <div class="grid-container">
          <div v-for="(proyecto, index) in proyectos" :key="index" class="card">
            <img :src="proyecto.imagen" :alt="proyecto.titulo" class="card-img" />
            <div class="card-content">
              <h3 class="card-title">{{ proyecto.titulo }}</h3>
              <p class="card-description">{{ proyecto.descripcion }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!--FORMULARIOOOO-->
    <div class="container1" id="CONTACTOFORMULARIO">
      <div class="form-box2">
        <h2 class="title1">Contacto</h2>
        <div class="divider2"></div>

        <form @submit.prevent="submitForm">
          <div class="form-group1">
            <label for="name">Nombre</label>
            <input type="text" id="name" v-model="form.name" required />
          </div>

          <div class="form-group1">
            <label for="email">Email</label>
            <input type="email" id="email" v-model="form.email" required />
          </div>

          <div class="form-group1">
            <label for="message">Mensaje</label>
            <textarea id="message" v-model="form.message" required></textarea>
          </div>

          <button type="submit" class="submit-btn2">Enviar Mensaje</button>
        </form>
      </div>
    </div>
  </main>
</template>

<script>
import Imagen1 from '../assets/Imagen1.jpg';
import Imagen2 from '../assets/Imagen2.jpg';
import Imagen3 from '../assets/Imagen3.jpg';
import Imagen4 from '../assets/Imagen4.jpg';
import Imagen5 from '../assets/Imagen5.jpg';
import Imagen6 from '../assets/Imagen6.jpg';
import profileImage from '../assets/profile.jpg';

export default {
  name: 'HomeComponent',
  data() {
    return {
      profileImage,
      proyectos: [
        {
          imagen: Imagen1,
          titulo: "GO-AM Reality Horizons",
          descripcion: "Lorem ipsum, dolor sit amet consectetur adipisicing elit...",
        },
        {
          imagen: Imagen2,
          titulo: "Valentín Dorantes - Fotografía y Video",
          descripcion: "Lorem ipsum, dolor sit amet consectetur adipisicing elit...",
        },
        {
          imagen: Imagen3,
          titulo: "XIB Creative",
          descripcion: "Lorem ipsum, dolor sit amet consectetur adipisicing elit...",
        },
        {
          imagen: Imagen4,
          titulo: "Camisetas personalizadas",
          descripcion: "Lorem ipsum, dolor sit amet consectetur adipisicing elit...",
        },
        {
          imagen: Imagen5,
          titulo: "VIII Festival Cultural Italiano",
          descripcion: "Lorem ipsum, dolor sit amet consectetur adipisicing elit...",
        },
        {
          imagen: Imagen6,
          titulo: "App de Café",
          descripcion: "Lorem ipsum, dolor sit amet consectetur adipisicing elit...",
        },
      ],
      // Datos del formulario de contacto
      form: {
        name: "",
        email: "",
        message: "",
      }
    };
  },
  methods: {
    submitForm() {
      console.log("Formulario enviado:", this.form);
      alert("Mensaje enviado con éxito");

      // Limpiar los campos después del envío
      this.form.name = "";
      this.form.email = "";
      this.form.message = "";
    },
    // Método para desplazarse a la sección
    scrollToSection(id) {
      const section = document.getElementById(id);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
    },
  },
};
</script>


<style scoped>

/* PARTE DEL PORTAFOLIO*/


.hero {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  margin-top: 50px;
}

.hero-content {
  max-width: 900px;
  width: 100%;
}

.hero-text {
  text-align: center;
  padding: 20px;
}

.hero-text h1 {
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
}

.hero-text h2 {
  font-size: 1.2rem;
  font-weight: normal;
}

/* PARTE SOBRE MÍ */

.about {
  padding: 50px 20px;
  text-align: center;
  max-width: 1200px;
  margin: -20px auto;
  
}

.aabout {
  padding: 50px 0;
}

.about-content {
  display: flex;
  align-items: center;
  flex-direction: row;
  gap: 2rem;
}

/* Imagen de perfil */
.profile-image {
  width: 250px;
  height: auto;
  object-fit: cover;
  border-radius: 15px;
}

/* Texto de sobre mí */
.about-text {
  flex: 1;
  text-align: left;

}

/* RESPONSIVIDAD */

/* Tablets */
@media (max-width: 1024px) {
  .hero-text h1 {
    font-size: 2rem;
    margin-top: 50px;
  }

  .hero-text h2 {
    font-size: 1rem;
  }

  .about-content {
    flex-direction: column;
    text-align: center;
  }

  .about-text {
    text-align: center;
  }
}

/* Móviles */
@media (max-width: 600px) {
  .hero {
    padding: 30px 15px;
  }

  .hero-text h1 {
    font-size: 1.8rem;
  }

  .hero-text h2 {
    font-size: 0.9rem;
  }

  .about {
    padding: 30px 15px;
  }

  .profile-image {
    width: 180px;
  }

  .about-content {
    flex-direction: column;
    gap: 1.5rem;
  }

  .about-text {
    text-align: center;
  }
}

/* PARTE DE GALERÍA DE PROYECTOS DE LAS IMAGENES ESAS*/

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.title {
  text-align: left;
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 20px;
}

/* ESTILOS DE IMAGENES EN SU CUADRITO (CARDS) */

.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.card {
  background: white;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.card-img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.card-content {
  padding: 15px;
}

.card-title {
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 10px;
}

.card-description {
  font-size: 14px;
  color: #666;
}


/*FORMULARIOOOOO*/
/* PARTE PRINCIPAL */
.container1 {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 50px 20px;
}

/* CAJA DEL FORMULARIO */
.form-box2 {
  background: white;
  padding: 30px;
  border-radius: 10px;
  width: 100%;
  max-width: 500px;
  text-align: center;
}

/* Título */
.title1 {
  font-size: 24px;
  font-weight: bold;
  color: #333;
  margin-bottom: 10px;
}

/* Línea divisora */
.divider2 {
  width: 50px;
  height: 3px;
  background-color: #1f2a38;
  margin: 0 auto 20px auto;
}

/* Grupos de formulario */
.form-group1 {
  text-align: left;
  margin-bottom: 15px;
}

.form-group1 label {
  display: block;
  font-weight: bold;
  color: #555;
  margin-bottom: 5px;
}

/* Campos de entrada */
.form-group1 input,
.form-group1 textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
}

.form-group1 textarea {
  resize: none;
  height: 120px;
}

/* Botón de enviar */
.submit-btn2 {
  width: 100%;
  background: #1f2a38;
  color: white;
  font-size: 16px;
  font-weight: bold;
  padding: 12px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.3s;
}

.submit-btn2:hover {
  background: #0056b3;
}


/* RESPONSIVIDAD DEL FOORMULARIO */
/* Pantallas d tablets */
@media (max-width: 768px) {
  .container1 {
    padding: 30px 15px;
    margin-right: 20px;
  }
  
  .form-box2 {
    padding: 20px;
  }
}

/* Pantallas pare cel */
@media (max-width: 480px) {
  .container1 {
    padding: 20px 10px;
  }

  .form-box2 {
    padding: 15px;
    width: 90%;
  }

  .title1 {
    font-size: 20px;
  }

  .submit-btn2 {
    font-size: 14px;
    padding: 10px;
  }
}
</style>
