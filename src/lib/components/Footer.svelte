<footer class="main wrappered">
	<h1>Angel Raymondi</h1>
	<div class="container">
		<div class="column">
			<p><span>Redes sociales</span></p>
			<ul>
				<li>Hola1</li>
				<li>Hola2</li>
				<li>Hola3</li>
			</ul>
		</div>
		<div class="column">
			<p><span>Column</span></p>
			<ul>
				<li>Hola1</li>
				<li>Hola2</li>
				<li>Hola3</li>
			</ul>
		</div>
		<div class="column">
			<p><span>Column</span></p>
			<ul>
				<li>Hola1</li>
				<li>Hola2</li>
				<li>Hola3</li>
			</ul>
		</div>
	</div>
</footer>
<footer class="love wrappered">
	<p>Hecho con ❤️ por <a href="https://github.com/angelraymondi">@angelraymondi</a></p>
</footer>

<style lang="scss">
	@use '#styles/variables' as *;

	footer.main {
		background: rgb(20, 20, 20);
		padding: 50px 30px;
		color: rgb(210, 210, 210);

		& > h1 {
			color: white;
			margin-bottom: 10px;
			font-size: 2.1em;
		}

		p {
			line-height: 1.7;
		}

		.container {
			display: grid;
			grid-template-columns: repeat(auto-fit, minmax(40ch, 1fr));
			gap: 20px;

			.column {
				p:first-child {
					position: relative;

					&::before {
						content: '';
						position: absolute;
						height: 2px;
						width: 100%;
						background: rgba(255, 255, 255, 0.08);
						top: 50%;
						transform: translateY(-50%);
					}

					& > span {
						font-size: 1.2em;
						font-weight: 450;
						color: white;
						position: relative;
						background: rgb(20, 20, 20);
						padding-right: 1ch;
						text-transform: uppercase;
						letter-spacing: 0.3px;
					}
				}

				ul {
					list-style: none;
					display: flex;
					flex-direction: column;
					gap: 5px;
				}
			}
		}
	}

	footer.love {
		background-color: $lime-green;
		padding: 10px 15px;

		p {
			text-align: center;
			line-height: 1.7;
			user-select: none;
		}

		a {
			color: inherit;
			text-decoration: underline;
			font-weight: 600;
			text-decoration-thickness: 1.5px;
		}
	}
</style>
