<script>

	import SectionNav from "./SectionNav.svelte";

</script>
<section>
	<div class="wrapper">
		<div class="image-container">
      <div class="image"></div>
    </div>
		<div class="text-container">
      <SectionNav inherit>Sobre mí</SectionNav>
			<h1>Lorem ipsum dolor sit.</h1>
      <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Maiores itaque doloremque ipsam eius labore nesciunt!</p>
		</div>
	</div>
</section>

<style lang="scss">
	@use '#styles/variables' as *;

	section {
		background-color: $lime-green;
		background-image: url(/doodles/summer.svg);

		.wrapper {
			padding: 50px 30px;
			display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
      place-content: center;
		}

    h1 {
      font-size: 2.5em;
      margin-bottom: 10px;
    }

    p {
      line-height: 1.8;
    }
	}

  .image-container {
    display: grid;
    place-items: center;
  }

  .image-container > .image {
    aspect-ratio: 1/1;
    background: white;
    border-radius: 50%;
    display: block;
    width: 80%;
  }

  .text-container {
    display: grid;
    place-content: center;
  }
</style>
