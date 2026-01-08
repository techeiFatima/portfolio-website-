<section id="skills" class="section-padding">
  <div class="container">
    <h2 class="section-title">Technical Skills</h2>
    
    <div class="skills-wrapper">
      <div class="category">
        <h3>Languages</h3>
        <div class="chips">
          <span class="chip">Python</span>
          <span class="chip">JavaScript</span>
          <span class="chip">TypeScript</span>
          <span class="chip">HTML5</span>
          <span class="chip">CSS3</span>
          <span class="chip">SQL</span>
        </div>
      </div>

      <div class="category">
        <h3>Machine Learning & AI</h3>
        <div class="chips">
          <span class="chip">PyTorch</span>
          <span class="chip">TensorFlow</span>
          <span class="chip">Scikit-learn</span>
          <span class="chip">Pandas</span>
          <span class="chip">NumPy</span>
          <span class="chip">Hugging Face</span>
          <span class="chip">OpenCV</span>
        </div>
      </div>

      <div class="category">
        <h3>Web Technologies</h3>
        <div class="chips">
          <span class="chip">React</span>
          <span class="chip">Svelte/SvelteKit</span>
          <span class="chip">Next.js</span>
          <span class="chip">Node.js</span>
          <span class="chip">Git/GitHub</span>
          <span class="chip">Linux</span>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .section-padding {
    padding: 100px 0;
    background: var(--bg-color);
  }

  .section-title {
    font-size: 2.5rem;
    text-align: center;
    margin-bottom: 60px;
    color: var(--text-main);
  }

  .skills-wrapper {
    display: flex;
    flex-direction: column;
    gap: 48px;
    max-width: 800px;
    margin: 0 auto;
  }

  .category h3 {
    font-size: 1.25rem;
    color: var(--primary-dark);
    margin-bottom: 16px;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: 700;
  }

  .chips {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
  }

  .chip {
    padding: 10px 20px;
    background: white;
    box-shadow: 0 2px 4px rgba(0,0,0,0.05);
    border-radius: var(--radius-full);
    font-size: 1rem;
    color: var(--text-main);
    font-weight: 500;
    transition: all 0.2s ease;
    border: 1px solid transparent;
  }

  .chip:hover {
    border-color: var(--primary);
    transform: translateY(-2px);
    background: var(--secondary);
    color: var(--primary-dark);
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  }
</style>
