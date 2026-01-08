<section id="experience" class="section-padding">
  <div class="container">
    <h2 class="section-title">Experience</h2>
    
    <div class="grid">
      <!-- MIT CSAIL -->
      <div class="card">
        <div class="header">
          <h3>AI Researcher</h3>
          <span class="company">MIT CSAIL</span>
        </div>
        <p class="description">
          Conducting research on AI fairness using <strong>CLIP</strong> and <strong>FairFace</strong>. Developing methods to detect and mitigate bias in large-scale vision-language models using PyTorch.
        </p>
        <div class="tags">
          <span class="tag">PyTorch</span>
          <span class="tag">Python</span>
          <span class="tag">Data Fairness</span>
        </div>
      </div>

      <!-- AI/ML Intern -->
      <div class="card">
        <div class="header">
          <h3>AI/ML Engineer Intern</h3>
          <span class="company">Tech Startup</span>
        </div>
        <p class="description">
          Built AI-powered chatbots to assist entrepreneurs. Integrated LLM APIs with backend services to provide real-time business insights.
        </p>
        <div class="tags">
          <span class="tag">LLMs</span>
          <span class="tag">Node.js</span>
          <span class="tag">API Integration</span>
        </div>
      </div>

      <!-- Frontend Dev -->
      <div class="card">
        <div class="header">
          <h3>Frontend Web Developer</h3>
          <span class="company">Freelance</span>
        </div>
        <p class="description">
          Designed and developed responsive websites for clients. Focused on clean UI/UX, accessibility, and performance optimization.
        </p>
        <div class="tags">
          <span class="tag">React</span>
          <span class="tag">JavaScript</span>
          <span class="tag">CSS3</span>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .section-padding {
    padding: 60px 0;
    background: var(--bg-color); /* Cream background to alternate */
  }

  .section-title {
    font-size: 2.5rem;
    text-align: center;
    margin-bottom: 60px;
    color: var(--text-main);
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 32px;
  }

  .card {
    background: white;
    padding: 32px;
    border-radius: var(--radius-lg);
    box-shadow: var(--shadow-sm);
    transition: all 0.3s ease;
    border: 1px solid rgba(0,0,0,0.03);
  }

  .card:hover {
    transform: translateY(-8px);
    box-shadow: var(--shadow-lg);
    border-color: var(--primary);
  }

  .header {
    margin-bottom: 16px;
    border-bottom: 1px solid #eee;
    padding-bottom: 16px;
  }

  h3 {
    font-size: 1.25rem;
    margin-bottom: 4px;
    color: var(--text-main);
  }

  .company {
    font-size: 1rem;
    color: var(--primary-dark);
    font-weight: 500;
  }

  .description {
    font-size: 1rem;
    color: var(--text-main);
    margin-bottom: 24px;
    height: 80px; /* consistent height */
  }

  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tag {
    font-size: 0.85rem;
    padding: 6px 12px;
    background: var(--secondary);
    color: var(--text-main);
    border-radius: var(--radius-full);
    font-weight: 500;
  }
</style>
