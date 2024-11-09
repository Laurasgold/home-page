<div>
  <nav>
    <a href="#about">About Me</a>
    <a href="#social">Social</a>
    <a href="#mission"> My Mission</a>
    <a href="#portfolio">Portfolio</a>
    <a href="#contact-me">Contact Me</a>
  </nav>
</div>

<style>
  nav {
    display: flex;
    justify-content: space-between;
    max-width: 1028px;
    margin: 0 auto;
    flex-wrap: wrap;
    gap: 1rem;
    align-items: center;

    @media screen and (max-width: 950px) {
      flex-direction: column;
    }
  }

  div {
    background: var(--warm-sand);
    border-top: 2px var(--dark-sage) solid;
    border-bottom: 2px var(--dark-sage) solid;
    padding: 2rem 1rem;
    font-size: var(--font-size-xsmall);
    font-family: var(--title-font);
  }
</style>
