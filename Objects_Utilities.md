```html
<section  class="o-row o-row--lg u-pt-clear">
	<div  class="o-container">
		<div  class="o-section o-section--lg">
			<figure>
				<img  src="img/jpg/intro-img.jpg"  alt="Dr. James Hamrick & Sarika Vora in their weekly team stand-up">
			</figure>
		</div>
		<div  class="o-section o-section--lg"></div>
			<div  class="o-layout o-layout--gutter-lg">
				<div  class="o-layout__item u-1-of-2-bp3">
					<div  class="u-max-width-sm">
						<h1  class="c-lead c-lead--xxl u-color-primary-base">
							Cancer is smart. <br>
							Together, we can <br>
							be smarter.
						</h1>
					</div>
				</div>
				<div  class="o-layout__item u-1-of-2-bp3">
					<div  class="u-max-width-sm">
						<p  class="c-lead c-lead--lg">
							Accelerating the fight against cancer requires the entire industry to work together. Our products 					 connect community oncologists, academics, hospitals, life science researchers and regulators on a shared technology platform. <br>
							Together, we can learn from the experience of every patient.
						</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
```
## Object: row
Een row is een horizontale rij die de hele viewport inneemt en padding toevoegt rond de children.
```css
.o-row {
	position: relative;
	padding: 24px  24px  0;
	display: flow-root;
}
```
- **Position: relative** zorgt ervoor dat ...
- 24px aan elke kant ...
- **display: flow-root** zorgt ervoor dat ...

## Object: container
Een container creëert een horizontale gecentreerde container die de globale maximum breedte bepaalt van de pagina, zodat die niet eindeloos breder kan worden.
_Containers zitten in rows. Containers kunnen wel in containers geplaatst worden._
```css
.o-container {
	margin-left: auto;
	margin-right: auto;
	width: 100%;
	max-width: 90em;
	/* Omgerekend naar em (90*16px = 1440px) */
	/* 1em = 16px hier */
}
```



## Utility: max-width
Met de max-width utilities kunnen we de maximum breedte overscrhijven als dat nodig is.
_We maken daar een utility van omdat we dat op andere element, objecten en componenten willen kunnen toepassen._
```css
.u-max-width-sm {
	max-width: 36em  !important;
}

.u-max-width-md {
	max-width: 45em  !important;
}

.u-max-width-lg {
	max-width: 60em  !important;
}

.u-max-width-xl {
	max-width: 75em  !important;
}

.u-max-width-none {
	max-width: none !important;
}
```

# Layout system
## Object: layout
Met het layout object kan je talloze responsive grid varianten maken.
Het bestaat uit de block: o-layout en het element: o-layout__item.

De block maakt gebruik van flexbox om elementen naast elkaar te plaatsen.

Met modifiers bepalen we de gutter op de items. Daarnaast heeft het heel wat modifiers die de horizontal en verticale alignering van items bepaalt en om bijvoorbeeld items te reversen.
```css
.o-layout {
	display: -webkit-flex;
	display: -ms-flexbox;
	display: flex;
	flex-wrap: wrap;
}

.o-layout__item {
	width: 100%;
}
```

```css
.u-flex-basis-auto {
	flex-basis: auto !important;
}

.u-flex-grow-1 {
	flex-grow: 1  !important;
}

.u-1-of-2 {
	flex-basis: calc(100% / 2) !important;
}
```
-   u-1-of-2 = calc(100% / 2) = 50%
-   u-1-of-3 = calc(100% / 3) = 33.3333333333%
-   u-1-of-4 = calc(100% / 4) = 25%
-   u-1-of-5 = calc(100% / 5) = 20%
-   u-1-of-6 = calc(100% / 6) = 16.6666666667%

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjQ3NzY3OTY2LDE0NzY3MDEwMDQsNTU5MD
AwMzU3LDM1Njk3NjA1MSwzODk3OTE4MzEsODAzMDc5MjgwXX0=

-->