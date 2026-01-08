<script lang="ts">
  import { onMount } from 'svelte';

  let cards: HTMLElement[] = [];

  function handleMouseMove(e: MouseEvent, index: number) {
    const card = cards[index];
    if (!card) return;

    const rect = card.getBoundingClientRect();
    const x = e.clientX - rect.left;
    const y = e.clientY - rect.top;

    const centerX = rect.width / 2;
    const centerY = rect.height / 2;

    const rotateX = ((y - centerY) / centerY) * -5; // Max 5deg rotation
    const rotateY = ((x - centerX) / centerX) * 5;

    card.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) scale3d(1.02, 1.02, 1.02)`;
  }

  function handleMouseLeave(index: number) {
    const card = cards[index];
    if (!card) return;
    
    card.style.transform = 'perspective(1000px) rotateX(0) rotateY(0) scale3d(1, 1, 1)';
  }
</script>

<section id="projects" class="section-padding">
  <div class="container">
    <h2 class="section-title">Selected Works</h2>
    
    <div class="grid">
      <!-- Project 1 -->
      <div 
        class="project-card" 
        role="group" 
        bind:this={cards[0]}
        onmousemove={(e) => handleMouseMove(e, 0)}
        onmouseleave={() => handleMouseLeave(0)}
      >
        <div class="image-placeholder gradient-1">
          <span>Vision-Language Fairness</span>
        </div>
        <div class="content">
          <h3>Debiasing VL Models</h3>
          <p>
            Research project investigating social bias in CLIP embeddings using the FairFace dataset. Implemented mitigation strategies to reduce gender and racial bias.
          </p>
          <div class="tags">
            <span class="tag">Python</span>
            <span class="tag">PyTorch</span>
            <span class="tag">Research</span>
          </div>
          <a href="#" class="link">Read Paper &rarr;</a>
        </div>
      </div>

      <!-- Project 2 -->
      <div 
        class="project-card" 
        role="group"
        bind:this={cards[1]}
        onmousemove={(e) => handleMouseMove(e, 1)}
        onmouseleave={() => handleMouseLeave(1)}
      >
        <div class="image-placeholder gradient-2">
          <span>Deep Learning Architecture</span>
        </div>
        <div class="content">
          <h3>CNN Image Classifier</h3>
          <p>
            Built a Convolutional Neural Network from scratch to classify complex image datasets with high accuracy. Explored ResNet and VGG architectures.
          </p>
          <div class="tags">
            <span class="tag">TensorFlow</span>
            <span class="tag">CNNs</span>
            <span class="tag">Vision</span>
          </div>
          <a href="#" class="link">View Code &rarr;</a>
        </div>
      </div>

      <!-- Project 3 -->
      <div 
        class="project-card" 
        role="group"
        bind:this={cards[2]}
        onmousemove={(e) => handleMouseMove(e, 2)}
        onmouseleave={() => handleMouseLeave(2)}
      >
        <div class="image-placeholder gradient-3">
          <span>Interactive AI</span>
        </div>
        <div class="content">
          <h3>Live Digit Recognition</h3>
          <p>
             An interactive web app that recognizes user-drawn digits in real-time. Bridging the gap between ML models and frontend interactivity.
          </p>
          <div class="tags">
            <span class="tag">React</span>
            <span class="tag">Flask</span>
            <span class="tag">WebSockets</span>
          </div>
          <a href="#" class="link">Try Demo &rarr;</a>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .section-padding {
    padding: 100px 0;
    background: white;
  }

  .section-title {
    font-size: 2.5rem;
    text-align: center;
    margin-bottom: 80px;
    color: var(--text-main);
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 40px;
  }

  .project-card {
    border-radius: var(--radius-lg);
    background: white;
    box-shadow: var(--shadow-sm);
    transition: transform 0.1s ease-out, box-shadow 0.3s ease; /* Fast transform for tilt */
    border: 1px solid rgba(0,0,0,0.05);
    display: flex;
    flex-direction: column;
    overflow: hidden;
    will-change: transform;
    transform-style: preserve-3d;
  }

  .project-card:hover {
    box-shadow: var(--shadow-lg);
    z-index: 10;
  }

  .image-placeholder {
    height: 240px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-weight: 700;
    font-size: 1.1rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    transition: filter 0.3s ease;
  }

  .project-card:hover .image-placeholder {
    filter: brightness(1.1);
  }

  .gradient-1 { background: linear-gradient(135deg, #a7d0e4, #eebec2); }
  .gradient-2 { background: linear-gradient(135deg, #e0bbe4, #957dad); }
  .gradient-3 { background: linear-gradient(135deg, #ffdfd3, #d291bc); }

  .content {
    padding: 40px;
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    background: rgba(255,255,255,0.8);
    backdrop-filter: blur(10px);
  }

  h3 {
    font-size: 1.5rem;
    margin-bottom: 12px;
    color: var(--text-main);
  }

  p {
    font-size: 1.05rem;
    color: var(--text-muted);
    line-height: 1.6;
    margin-bottom: 24px;
    flex-grow: 1;
  }

  .tags {
    display: flex;
    gap: 8px;
    margin-bottom: 32px;
    flex-wrap: wrap;
  }

  .tag {
    font-size: 0.75rem;
    padding: 6px 14px;
    border: 1px solid rgba(0,0,0,0.08); /* Minimal border */
    background: transparent;
    color: var(--text-main);
    border-radius: var(--radius-full);
    text-transform: uppercase;
    font-weight: 600;
    letter-spacing: 0.5px;
  }

  .link {
    font-weight: 600;
    color: var(--text-main);
    font-size: 1rem;
    border-bottom: 1px solid var(--primary);
    display: inline-block;
    width: fit-content;
    padding-bottom: 2px;
  }

  .link:hover {
    color: var(--primary-dark);
    border-bottom-color: var(--primary-dark);
  }
</style>
