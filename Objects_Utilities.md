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
### Modifiers
#### Gutter modifiers
De gutter modifiers zorgen voor een padding links en rechts van de elementen, maar niet aan de buitenste zijkanten.

```css
/* Dit haalt padding weg uiterst links en uiterst rechts,
zodat er enkel padding is TUSSEN de elementen */
.o-layout--gutter {
	margin: 0  -12px;
}

/* Padding L&R van elk child met de klasse o-layout__item */
.o-layout--gutter > .o-layout__item {
	padding: 0  12px;
}

/*
.o-layout--gutter-sm = 6px
.o-layout--gutter-lg = 24px
*/
```

#### Reverse horizontal row modifier
Plaatst de rij in omgekeerde volgorde, zonder de HTML volgorde te wijzigen.
```css
.o-layout--row-reverse {
	flex-flow: row-reverse;
}
```
#### Reverse horizontal row modifier
Plaatst de rij in omgekeerde volgorde, zonder de HTML volgorde te wijzigen.
```css
.o-layout--row-reverse {
	flex-flow: row-reverse;
}
```

#### Horizontal alignment modifiers
Justify-content bepaalt de verdeling van de items op de main-axis.
Alleen effect als breedte container > breedte alle items.
```css
/* Items staan tegen de main-start */
.o-layout--justify-start {}

/* Items staan tegen de main-end (volgorde blijft gelijk) */
.o-layout--justify-end {
	justify-content: flex-end;
}

/* Links en rechts van de items is evenveel plaats */
.o-layout--justify-center {
	justify-content: center;
}

/* Links en rechts van het item is evenveel plaats */
/* x ITEM x*2 ITEM x*2 ITEM x */
.o-layout--justify-space-around {
	justify-content: space-around;
}

/* Tussen de items is evenveel plaats */
/* Eerste en laatste item plakken tegen de buitenrand */
/* ITEM x ITEM x ITEM */
.o-layout--justify-space-between {
	justify-content: space-between;
}

/* Tussen de items is evenveel plaats */
/* x ITEM x ITEM x ITEM x */
.o-layout--justify-space-evenly {
	justify-content: space-evenly;
}
```
#### Vertical alignment modifiers
Justify-content bepaalt de verdeling van de items op de main-axis.
Alleen effect als breedte container > breedte alle items.


## Utilities
### Flex-basis & flex-grow
Met u-x-of-y kan de flex-basis (grootte) van een o-layout__item aanpassen.
_De breedte is dan x/y van de volledige breedte (bv 4/5e)_
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
Je kan dit ook instellen vanaf bepaalde breakpoints.
Items worden dus pas x/y van de volledige breedte vanaf een bepaalde min-width.
```css
@media (min-width: 576px) {
	.u-1-of-2-bp1 {
		flex-basis: calc(100% / 2) !important;
	}
}

/* bp1 = 576px */
/* bp2 = 768px */
/* bp3 = 992px */
/* bp4 = 1200px */
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbOTQ5NTY3NjcwLDgzOTIzNzM4MSwxNDc2Nz
AxMDA0LDU1OTAwMDM1NywzNTY5NzYwNTEsMzg5NzkxODMxLDgw
MzA3OTI4MF19
-->