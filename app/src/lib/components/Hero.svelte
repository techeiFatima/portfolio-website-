<script lang="ts">
  import { onMount } from 'svelte';
  import { fade, fly } from 'svelte/transition';

  let visible = false;

  onMount(() => {
    visible = true;
  });
</script>

<section class="hero">
  <!-- Dynamic Background -->
  <div class="blob-bg"></div>

  <div class="container hero-grid">
    <div class="text-side">
      {#if visible}
        <h2 in:fly="{{ y: 20, duration: 800, delay: 200 }}" class="eyebrow">
          MIT &middot; CSAIL &middot; Research
        </h2>
        
        <h1 in:fly="{{ y: 40, duration: 800, delay: 400 }}">
          Creating <br />
          <span class="italic">Intelligent</span> <br />
          Futures.
        </h1>
        
        <div class="bio" in:fly="{{ y: 20, duration: 800, delay: 600 }}">
          <p>
            I'm <strong>Fatima Danishyar</strong>. I bridge the gap between rigorous <strong>AI research</strong> and <strong>creative design</strong>. Building fairness into code and beauty into logic.
          </p>
        </div>

        <div class="actions" in:fly="{{ y: 20, duration: 800, delay: 800 }}">
          <a href="#projects" class="btn-link">
            Explore Work 
            <span class="arrow">&nearr;</span>
          </a>
        </div>
      {/if}
    </div>

    <div class="visual-side" in:fade="{{ duration: 1500, delay: 500 }}">
      <!-- Abstract 3D Representation -->
       <div class="glass-card floating">
          <div class="card-content">
            <span class="label">Current Focus</span>
            <h3>Debiasing Vision Models</h3>
            <div class="stat">
              <span class="num">98%</span>
              <span class="desc">Accuracy</span>
            </div>
          </div>
       </div>
       <div class="orbit-circle"></div>
    </div>
  </div>
</section>

<style>
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    overflow: hidden;
    padding-top: 60px;
  }

  .hero-grid {
    display: grid;
    grid-template-columns: 1.2fr 0.8fr;
    gap: 60px;
    align-items: center;
    width: 100%;
    z-index: 2;
  }

  /* Typography */
  .eyebrow {
    font-size: 0.9rem;
    text-transform: uppercase;
    letter-spacing: 3px;
    color: var(--primary-dark);
    margin-bottom: 32px;
    font-weight: 700;
    opacity: 0.8;
  }

  h1 {
    font-size: 6.5rem;
    line-height: 0.95;
    margin-bottom: 48px;
    letter-spacing: -2px;
    color: var(--text-main);
  }

  .italic {
    font-family: 'Playfair Display', serif; /* Or just italic styles */
    font-style: italic;
    font-weight: 300;
    background: var(--gradient-text);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .bio {
    max-width: 450px;
    margin-bottom: 48px;
  }

  .bio p {
    font-size: 1.25rem;
    line-height: 1.6;
    color: var(--text-muted);
  }

  strong {
    color: var(--text-main);
    font-weight: 600;
  }

  .btn-link {
    font-size: 1.2rem;
    font-weight: 600;
    border-bottom: 2px solid var(--primary);
    padding-bottom: 4px;
    display: inline-flex;
    align-items: center;
    gap: 8px;
  }

  .arrow {
    font-size: 1.5rem;
    transition: transform 0.3s ease;
  }

  .btn-link:hover .arrow {
    transform: translate(4px, -4px);
  }

  /* Visual Side */
  .visual-side {
    position: relative;
    height: 600px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .glass-card {
    width: 300px;
    height: 400px;
    background: rgba(255, 255, 255, 0.4);
    backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.6);
    border-radius: 30px;
    box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.1);
    z-index: 5;
    padding: 40px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transform: rotate(-5deg);
  }

  .floating {
    animation: float 6s ease-in-out infinite;
  }

  .card-content .label {
    text-transform: uppercase;
    font-size: 0.8rem;
    letter-spacing: 1px;
    color: var(--primary-dark);
  }

  .card-content h3 {
    font-size: 2rem;
    margin-top: 10px;
    line-height: 1.2;
  }

  .stat {
    margin-top: auto;
  }

  .stat .num {
    display: block;
    font-size: 3.5rem;
    font-weight: 700;
    color: var(--text-main);
  }

  .stat .desc {
    font-size: 0.9rem;
    color: var(--text-muted);
  }

  .orbit-circle {
    position: absolute;
    width: 400px;
    height: 400px;
    border: 1px solid rgba(149, 125, 173, 0.2);
    border-radius: 50%;
    z-index: 1;
  }

  .blob-bg {
    position: absolute;
    top: -20%;
    right: -10%;
    width: 800px;
    height: 800px;
    background: radial-gradient(circle, rgba(255,223,211,0.4) 0%, rgba(224,187,228,0.1) 60%, transparent 80%);
    filter: blur(60px);
    z-index: 0;
  }

  @keyframes float {
    0% { transform: translateY(0px) rotate(-5deg); }
    50% { transform: translateY(-20px) rotate(-3deg); }
    100% { transform: translateY(0px) rotate(-5deg); }
  }

  @media (max-width: 900px) {
    .hero-grid {
      grid-template-columns: 1fr;
      text-align: center;
    }
    .text-side {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    h1 { font-size: 3.5rem; }
    .visual-side { display: none; }
  }
</style>
