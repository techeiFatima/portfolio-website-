<section id="contact" class="footer">
  <div class="container content">
    <h2>Let's build thoughtful AI together.</h2>
    <p>
      I'm always open to discussing new opportunities in AI research and software engineering.
    </p>
    
    <div class="buttons">
      <a href="mailto:fatima@example.com" class="btn btn-email">Get in Touch</a>
      <a href="https://linkedin.com" target="_blank" rel="noreferrer" class="btn btn-linkedin">LinkedIn</a>
    </div>

    <div class="copyright">
      &copy; {new Date().getFullYear()} Fatima Danishyar. Built with SvelteKit & Love.
    </div>
  </div>
</section>

<style>
  .footer {
    padding: 100px 0 40px;
    background: var(--primary-dark);
    color: white;
    text-align: center;
  }

  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  h2 {
    font-size: 3rem;
    color: white;
    margin-bottom: 24px;
    font-weight: 700;
  }

  p {
    font-size: 1.2rem;
    color: rgba(255, 255, 255, 0.9);
    margin-bottom: 48px;
    max-width: 600px;
  }

  .buttons {
    display: flex;
    gap: 20px;
    margin-bottom: 80px;
  }

  .btn {
    padding: 14px 32px;
    border-radius: var(--radius-full);
    font-weight: 600;
    font-size: 1.1rem;
    transition: all 0.3s ease;
  }

  .btn-email {
    background: white;
    color: var(--primary-dark);
  }

  .btn-email:hover {
    background: var(--secondary);
    transform: translateY(-3px);
  }

  .btn-linkedin {
    background: rgba(255, 255, 255, 0.2);
    border: 1px solid rgba(255, 255, 255, 0.4);
    color: white;
    backdrop-filter: blur(4px);
  }

  .btn-linkedin:hover {
    background: white;
    color: var(--primary-dark);
    transform: translateY(-3px);
  }

  .copyright {
    font-size: 0.9rem;
    color: rgba(255, 255, 255, 0.6);
    border-top: 1px solid rgba(255, 255, 255, 0.2);
    width: 100%;
    padding-top: 32px;
  }

  @media (max-width: 768px) {
    h2 { font-size: 2rem; }
  }
</style>
