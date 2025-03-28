<nav class="wrapper">
  <div>
    <h1>Lorem, ipsum.</h1>
  </div>
  <div></div>
  <!-- TODO: Completar -->
</nav>

<style lang="scss">
  nav {
    display: flex;
    justify-content: space-between;
    width: calc(100% - 30px);
    left: 50%;
    top: 15px;
    transform: translateX(-50%);
    position: fixed;
    background: rgba(0, 0, 0, .1);
    height: 55px;
    padding: 5px 20px;
    backdrop-filter: blur(20px);
    border-radius: .75em;
    align-items: center;
    z-index: 50;

    h1 {
      font-size: 1.2em;
      font-weight: 400;
    }
  }
</style>