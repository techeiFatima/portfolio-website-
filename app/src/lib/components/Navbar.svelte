<script lang="ts">
  import { onMount } from 'svelte';
  
  let y: number = 0;
  let mobileMenuOpen = false;

  function toggleMenu() {
    mobileMenuOpen = !mobileMenuOpen;
  }
</script>

<svelte:window bind:scrollY={y} />

<nav class:scrolled={y > 50} class:open={mobileMenuOpen}>
  <div class="container nav-content">
    <a href="/" class="logo">Fatima<span class="dot">.</span></a>

    <div class="desktop-links">
      <a href="#projects">Work</a>
      <a href="#contact" class="btn-contact">Contact</a>
    </div>

    <button class="menu-toggle" aria-label="Toggle Menu" onclick={toggleMenu}>
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </button>
  </div>

  {#if mobileMenuOpen}
    <div class="mobile-links">
      <a href="#projects" onclick={toggleMenu}>Work</a>
      <a href="#contact" onclick={toggleMenu}>Contact</a>
    </div>
  {/if}
</nav>

<style>
  nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 80px;
    z-index: 1000;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
  }

  nav.scrolled {
    background: rgba(253, 252, 254, 0.85); /* Semi-transparent bg */
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.3);
    box-shadow: var(--shadow-sm);
    height: 70px;
  }

  .nav-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
  }

  .logo {
    font-family: var(--font-heading);
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--text-main);
  }

  .dot {
    color: var(--primary);
  }

  .desktop-links {
    display: flex;
    gap: 32px;
    align-items: center;
  }

  .desktop-links a {
    font-weight: 500;
    font-size: 0.95rem;
    color: var(--text-main);
    position: relative;
  }

  .desktop-links a:hover {
    color: var(--primary-dark);
  }

  .btn-contact {
    padding: 8px 20px;
    background: var(--primary);
    color: white !important;
    border-radius: var(--radius-full);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .btn-contact:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(224, 187, 228, 0.4);
    background: var(--primary-dark);
  }

  .menu-toggle {
    display: none;
    flex-direction: column;
    gap: 6px;
    background: none;
  }

  .bar {
    width: 24px;
    height: 2px;
    background: var(--text-main);
    transition: 0.3s;
  }

  /* Mobile Styles */
  .mobile-links {
    display: none;
  }

  @media (max-width: 768px) {
    .desktop-links {
      display: none;
    }

    .menu-toggle {
      display: flex;
    }

    nav.open {
      background: var(--bg-color);
      height: auto;
      flex-direction: column;
      padding-bottom: 24px;
    }

    .mobile-links {
      display: flex;
      flex-direction: column;
      gap: 24px;
      text-align: center;
      width: 100%;
      padding-top: 24px;
    }
  }
</style>
