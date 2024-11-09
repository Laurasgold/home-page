<footer>
  <h3 class="flex-start">Laura Goldthwaite</h3>
  <nav>
    <a href="#about">About Me</a>
    <a href="#social">Social</a>
    <a href="#mission"> My Mission</a>
    <a href="#portfolio">Portfolio</a>
    <a href="#contact-me">Contact Me</a>
  </nav>
  <span class="flex-start date">{new Date().getFullYear()}</span>
</footer>

<style>
  h3 {
    padding: 1.5rem 0;
  }

  nav {
    text-align: right;
    gap: 1rem;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
  }
  a:hover {
    color: var(--sage);
  }
  .flex-start {
    display: flex;
    justify-content: flex-start;
  }
  .date {
    color: var(--sage);
  }

  footer {
    background: var(--dark-sage);
    padding: 2rem 1rem;
    font-size: var(--font-size-small);
    font-family: var(--title-font);
    color: var(--silver);
    padding-top: 150px;
  }

  @media screen and (max-width: 820px) {
    h3 {
      font-size: var(--font-size-small);
    }
    footer {
      font-size: 1rem;
    }
  }
</style>
