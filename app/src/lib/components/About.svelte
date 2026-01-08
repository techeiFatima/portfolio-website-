<section id="about" class="section-padding">
  <div class="container about-container">
    <div class="content">
      <h2 class="section-title">About Me</h2>
      <p class="summary">
        I am an <strong>MIT undergraduate</strong> studying <strong>Artificial Intelligence & Decision-Making</strong>, driven by a passion for ethical AI and human-centered systems.
      </p>
      <p>
        My work sits at the intersection of <strong>rigorous machine learning research</strong> and <strong>creative frontend engineering</strong>. I believe that powerful AI systems should not only be intelligent but also fair, accessible, and beautifully designed.
      </p>
      <p>
        Currently, I am researching AI fairness at <strong>MIT CSAIL</strong>, building tools to debias vision-language models. When I'm not training models, I'm designing fluid, interactive web experiences that make complex technology feel approachable.
      </p>
    </div>
  </div>
</section>

<style>
  .section-padding {
    padding: 100px 0;
    background: white;
  }

  .about-container {
    max-width: 800px;
    margin: 0 auto;
    text-align: center;
  }

  .section-title {
    font-size: 2.5rem;
    margin-bottom: 32px;
    color: var(--primary-dark);
    position: relative;
    display: inline-block;
  }

  .section-title::after {
    content: '';
    display: block;
    width: 60px;
    height: 4px;
    background: var(--gradient-text);
    margin: 8px auto 0;
    border-radius: var(--radius-full);
  }

  p {
    font-size: 1.15rem;
    color: var(--text-main);
    line-height: 1.8;
    margin-bottom: 24px;
  }

  .summary {
    font-size: 1.4rem;
    font-weight: 300;
    color: var(--text-main);
    margin-bottom: 40px;
  }

  strong {
    font-weight: 600;
    color: var(--primary-dark);
  }
</style>
