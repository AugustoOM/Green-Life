<script>
  // Importar imágenes
  import planta1 from './images/planta1.jpg';
  import planta2 from './images/planta2.jpg';
  import planta3 from './images/planta3.jpg';

  // Datos para las secciones
  const quienesSomos = {
    titulo: "¿Quiénes somos?",
    contenido: "Green Day es un ecommerce comprometido con la sostenibilidad y el cuidado del medio ambiente. Nuestra misión es ofrecer productos ecológicos de alta calidad que ayuden a nuestros clientes a llevar un estilo de vida más consciente y responsable con el planeta.",
    imagen: planta1
  };

  const queHacemos = {
    titulo: "¿Qué hacemos?",
    contenido: "Ofrecemos una amplia gama de productos sostenibles, desde artículos de uso diario hasta soluciones innovadoras para el hogar. Trabajamos directamente con proveedores que comparten nuestros valores de sostenibilidad, garantizando que cada producto en nuestro catálogo cumpla con los más altos estándares ambientales.",
    imagen: planta2
  };

  const porQueElegirnos = {
    titulo: "¿Por qué elegirnos?",
    razones: [
      {
        titulo: "Compromiso Ambiental",
        descripcion: "Cada producto está cuidadosamente seleccionado por su impacto positivo en el medio ambiente."
      },
      {
        titulo: "Calidad Garantizada",
        descripcion: "Trabajamos solo con proveedores certificados que cumplen estándares de sostenibilidad."
      },
      {
        titulo: "Experiencia del Cliente",
        descripcion: "Ofrecemos un servicio al cliente excepcional y una experiencia de compra sin complicaciones."
      },
      {
        titulo: "Precios Competitivos",
        descripcion: "Hacemos que los productos sostenibles sean accesibles para todos."
      }
    ],
    imagen: planta3
  };
</script>

<main>
  <!-- Hero Section -->
  <section class="hero">
    <div class="hero-content">
      <h1 class="hero-title">Green Day</h1>
      <p class="hero-subtitle">Tu ecommerce sostenible de confianza</p>
      <div class="hero-decoration"></div>
    </div>
  </section>

  <!-- Sección: ¿Quiénes somos? -->
  <section class="section quienes-somos" id="quienes-somos">
    <div class="container">
      <h2 class="section-title">{quienesSomos.titulo}</h2>
      <div class="content-wrapper">
        <div class="text-content">
          <p class="section-text">{quienesSomos.contenido}</p>
        </div>
        <div class="image-wrapper">
          <img src={quienesSomos.imagen} alt="Productos sostenibles Green Day" class="section-image" />
        </div>
      </div>
    </div>
  </section>

  <!-- Sección: ¿Qué hacemos? -->
  <section class="section que-hacemos" id="que-hacemos">
    <div class="container">
      <h2 class="section-title">{queHacemos.titulo}</h2>
      <div class="content-wrapper reverse">
        <div class="text-content">
          <p class="section-text">{queHacemos.contenido}</p>
        </div>
        <div class="image-wrapper">
          <img src={queHacemos.imagen} alt="Productos ecológicos Green Day" class="section-image" />
        </div>
      </div>
    </div>
  </section>

  <!-- Sección: ¿Por qué elegirnos? -->
  <section class="section por-que-elegirnos" id="por-que-elegirnos">
    <div class="container">
      <h2 class="section-title">{porQueElegirnos.titulo}</h2>
      <div class="image-gallery">
        <div class="gallery-image-wrapper">
          <img src={porQueElegirnos.imagen} alt="Sostenibilidad Green Day" class="gallery-image" />
        </div>
      </div>
      <div class="razones-grid">
        {#each porQueElegirnos.razones as razon}
          <div class="razon-card">
            <div class="card-icon">
              <div class="icon-circle"></div>
            </div>
            <h3 class="card-title">{razon.titulo}</h3>
            <p class="card-text">{razon.descripcion}</p>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="footer">
    <div class="container">
      <p class="footer-text">© 2025 Green Day. Todos los derechos reservados.</p>
    </div>
  </footer>
</main>

<style>
  main {
    min-height: 100vh;
  }

  /* Hero Section */
  .hero {
    background: linear-gradient(135deg, var(--verde-primario) 0%, var(--verde-secundario) 100%);
    color: var(--blanco);
    padding: 120px 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: -50%;
    right: -50%;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle, var(--dorado-primario) 0%, transparent 70%);
    opacity: 0.1;
    animation: rotate 20s linear infinite;
  }

  @keyframes rotate {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(360deg);
    }
  }

  .hero-content {
    position: relative;
    z-index: 1;
    max-width: 800px;
    margin: 0 auto;
  }

  .hero-title {
    font-size: 4.5rem;
    font-weight: 700;
    margin-bottom: 1rem;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
    color: var(--dorado-primario);
  }

  .hero-subtitle {
    font-size: 1.5rem;
    font-weight: 300;
    opacity: 0.95;
  }

  .hero-decoration {
    margin-top: 2rem;
    width: 100px;
    height: 4px;
    background: var(--dorado-primario);
    margin-left: auto;
    margin-right: auto;
    border-radius: 2px;
  }

  /* Secciones Generales */
  .section {
    padding: 80px 20px;
    position: relative;
  }

  .quienes-somos {
    background: var(--gris-claro);
  }

  .que-hacemos {
    background: var(--blanco);
  }

  .por-que-elegirnos {
    background: linear-gradient(135deg, var(--verde-muy-claro) 0%, var(--gris-claro) 100%);
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
  }

  .section-title {
    font-size: 3rem;
    font-weight: 700;
    text-align: center;
    margin-bottom: 3rem;
    color: var(--verde-primario);
    position: relative;
    display: inline-block;
    width: 100%;
  }

  .section-title::after {
    content: '';
    display: block;
    width: 80px;
    height: 4px;
    background: var(--dorado-primario);
    margin: 1rem auto 0;
    border-radius: 2px;
  }

  /* Content Wrapper */
  .content-wrapper {
    display: flex;
    align-items: center;
    gap: 3rem;
    flex-wrap: wrap;
  }

  .content-wrapper.reverse {
    flex-direction: row-reverse;
  }

  .text-content {
    flex: 1;
    min-width: 300px;
  }

  .section-text {
    font-size: 1.25rem;
    line-height: 1.8;
    color: var(--negro);
    text-align: justify;
  }

  /* Image Wrapper */
  .image-wrapper {
    flex: 0 0 400px;
    max-width: 100%;
    height: 400px;
    position: relative;
    border-radius: 16px;
    overflow: hidden;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .image-wrapper:hover {
    transform: translateY(-5px);
    box-shadow: 0 12px 32px rgba(0, 0, 0, 0.2);
  }

  .section-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    border-radius: 16px;
  }

  /* Image Gallery */
  .image-gallery {
    margin-bottom: 3rem;
    display: flex;
    justify-content: center;
  }

  .gallery-image-wrapper {
    max-width: 600px;
    width: 100%;
    border-radius: 16px;
    overflow: hidden;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .gallery-image-wrapper:hover {
    transform: scale(1.02);
    box-shadow: 0 12px 32px rgba(0, 0, 0, 0.2);
  }

  .gallery-image {
    width: 100%;
    height: auto;
    display: block;
    border-radius: 16px;
  }

  /* Razones Grid */
  .razones-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
    margin-top: 3rem;
  }

  .razon-card {
    background: var(--blanco);
    padding: 2.5rem 2rem;
    border-radius: 12px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    text-align: center;
    border-top: 4px solid var(--dorado-primario);
  }

  .razon-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
  }

  .card-icon {
    margin-bottom: 1.5rem;
    display: flex;
    justify-content: center;
  }

  .icon-circle {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--verde-secundario), var(--verde-claro));
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
  }

  .icon-circle::after {
    content: '✓';
    font-size: 2rem;
    color: var(--blanco);
    font-weight: bold;
  }

  .card-title {
    font-size: 1.5rem;
    font-weight: 600;
    color: var(--verde-primario);
    margin-bottom: 1rem;
  }

  .card-text {
    font-size: 1rem;
    line-height: 1.6;
    color: var(--negro);
  }

  /* Footer */
  .footer {
    background: var(--verde-primario);
    color: var(--blanco);
    padding: 2rem 20px;
    text-align: center;
  }

  .footer-text {
    font-size: 0.9rem;
    opacity: 0.9;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .hero-title {
      font-size: 3rem;
    }

    .hero-subtitle {
      font-size: 1.2rem;
    }

    .section-title {
      font-size: 2rem;
    }

    .section-text {
      font-size: 1.1rem;
    }

    .content-wrapper {
      flex-direction: column;
    }

    .content-wrapper.reverse {
      flex-direction: column;
    }

    .image-wrapper {
      flex: 0 0 100%;
      max-width: 100%;
      margin-top: 2rem;
    }

    .gallery-image-wrapper {
      max-width: 100%;
    }

    .razones-grid {
      grid-template-columns: 1fr;
    }
  }
</style>

