+++
archetype = "chapter"
title = "Chuleta Markdown"
weight = 4
+++

## Encabezados
```markdown
# Encabezado 1
## Encabezado 2
### Encabezado 3
#### Encabezado 4
##### Encabezado 5
```
# Encabezado 1
## Encabezado 2
### Encabezado 3
#### Encabezado 4
##### Encabezado 5

## Estilos de texto 
```markdown
Negrita
**El veloz zorro marrón salta sobre el perro perezoso.**
__El veloz zorro marrón salta sobre el perro perezoso.__

Cursiva
*El veloz zorro marrón salta sobre el perro perezoso.*
_El veloz zorro marrón salta sobre el perro perezoso._

Negrita y cursiva
**_El veloz zorro marrón salta sobre el perro perezoso._**

```
##### Negrita

**El veloz zorro marrón salta sobre el perro perezoso.**

__El veloz zorro marrón salta sobre el perro perezoso.__

##### Cursiva

*El veloz zorro marrón salta sobre el perro perezoso.*

_El veloz zorro marrón salta sobre el perro perezoso._

##### Negrita y cursiva

**_El veloz zorro marrón salta sobre el perro perezoso._**

##### Texto tachado

~~Strike through this text~~

##### Sustitución de texto

```markdown
Double quotes `"` and single quotes `'` of enclosed text are replaced by **"double curly quotes"** and **'single curly quotes'**.

Double dashes `--` and triple dashes `---` are replaced by en-dash **--** and em-dash **---** entities.

Double arrows pointing left `<<` or right `>>` are replaced by arrow **<<** and **>>** entities.

Three consecutive dots `...` are replaced by an ellipsis **...** entity.
```

Double quotes `"` and single quotes `'` of enclosed text are replaced by **"double curly quotes"** and **'single curly quotes'**.

Double dashes `--` and triple dashes `---` are replaced by en-dash **--** and em-dash **---** entities.

Double arrows pointing left `<<` or right `>>` are replaced by arrow **<<** and **>>** entities.

Three consecutive dots `...` are replaced by an ellipsis **...** entity.

## Listas

##### Desordenadas

Puede escribir una lista de elementos en la que el orden de los elementos no importe explícitamente.

Es posible anidar listas aplicando sangría a un elemento para el siguiente subnivel.

Puede utilizar cualquiera de -, *o +para indicar viñetas para cada elemento de la lista, pero no debe cambiar entre esos símbolos dentro de una lista completa.

```markdown
- Lorem ipsum dolor sit amet
- Consectetur adipiscing elit
  - Vestibulum laoreet porttitor sem
  - Ac tristique libero volutpat at
- Nulla volutpat aliquam velit
  - Phasellus iaculis neque
  - Purus sodales ultricies
- Faucibus porta lacus fringilla vel
```

- Lorem ipsum dolor sit amet
- Consectetur adipiscing elit
  - Vestibulum laoreet porttitor sem
  - Ac tristique libero volutpat at
- Nulla volutpat aliquam velit
  - Phasellus iaculis neque
  - Purus sodales ultricies
- Faucibus porta lacus fringilla vel

##### Ordenadas
Puede crear una lista de elementos en los que el orden de los elementos sí importa explícitamente.

Es posible anidar listas aplicando sangría a un elemento para el siguiente subnivel.

Markdown numerará automáticamente cada uno de sus artículos de forma consecutiva. Esto significa que el número de pedido que proporciona es irrelevante.

```markdown
1. Lorem ipsum dolor sit amet
3. Consectetur adipiscing elit
    1. Integer molestie lorem at massa
    7. Facilisis in pretium nisl aliquet
99. Nulla volutpat aliquam velit
    1. Faucibus porta lacus fringilla vel
    1. Aenean sit amet erat nunc
17. Eget porttitor lorem
```

1. Lorem ipsum dolor sit amet
1000. Consectetur adipiscing elit
    1. Integer molestie lorem at massa
    7. Facilisis in pretium nisl aliquet
99. Nulla volutpat aliquam velit
    1. Faucibus porta lacus fringilla vel
    1. Aenean sit amet erat nunc
17. Eget porttitor lorem

## CheckBox
En GFM (GitHub Flavored Markdown) puede agregar listas de tareas que dan como resultado elementos marcados o no marcados en los que no se puede hacer clic.

```markdown
- [x] Basic Test
- [ ] More Tests
  - [x] View
  - [x] Hear
  - [ ] Smell
```
- [x] Basic Test
- [ ] More Tests
  - [x] View
  - [x] Hear
  - [ ] Smell

## Definiciones

```markdown
Apple
: Pomaceous fruit of plants of the genus Malus in the family Rosaceae.
: An American computer company.

Orange
: The fruit of an evergreen tree of the genus Citrus.

  You can make juice out of it.
: A telecommunication company.

  You can't make juice out of it.
```

Apple
: Pomaceous fruit of plants of the genus Malus in the family Rosaceae.
: An American computer company.

Orange
: The fruit of an evergreen tree of the genus Citrus.

  You can make juice out of it.
: A telecommunication company.

  You can't make juice out of it.

## Código
##### Codigo en línea
Los fragmentos de código en línea se pueden incluir con comillas invertidas **`**.

```markdown
In this example, `<div></div>` is marked as code.
```

In this example, `<div></div>` is marked as code.

##### Bloque de código sangrado
Se puede generar un bloque de código simple sangrando varias líneas de código con al menos dos espacios.

```markdown
Dejate impresionado por mi codigo avanzado

    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code
```

Dejate impresionado por mi codigo avanzado
    
    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code

##### Bloque de código vallado

Si desea obtener más control de su bloque de código, puede encerrar su código con al menos tres comillas invertidas, ```lo que se conoce como valla.

En GFM (GitHub Flavored Markdown) también puede agregar un especificador de idioma directamente después de la valla de apertura, ```jsy el resaltado de sintaxis se aplicará automáticamente de acuerdo con el idioma seleccionado en el HTML renderizado.

```js
grunt.initConfig({
  assemble: {
    options: {
      assets: 'docs/assets',
      data: 'src/data/*.{json,yml}',
      helpers: 'src/custom-helpers.js',
      partials: ['src/partials/**/*.{hbs,md}']
    },
    pages: {
      options: {
        layout: 'default.hbs'
      },
      files: {
        './': ['src/templates/pages/index.hbs']
      }
    }
  }
};
```

## Tablas

Puede crear tablas agregando tuberías como divisores entre cada celda y agregando una línea de guiones (también separados por barras) debajo del encabezado.

```markdown
| Option | Description |
|--------|-------------|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
```

| Option | Description |
|--------|-------------|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |

##### Alineadas
Agregar dos puntos en el lado izquierdo y/o derecho de los guiones debajo de cualquier encabezado alineará el texto de esa columna en consecuencia.

```Markdown
| Option | Number | Description |
|-------:|:------:|:------------|
| data   | 1      | path to data files to supply the data that will be passed into templates. |
| engine | 2      | engine to be used for processing templates. Handlebars is the default. |
| ext    | 3      | extension to be used for dest files. |
```

| Option | Number | Description |
|-------:|:------:|:------------|
| data   | 1      | path to data files to supply the data that will be passed into templates. |
| engine | 2      | engine to be used for processing templates. Handlebars is the default. |
| ext    | 3      | extension to be used for dest files. |

## Citas en bloque
Para citar bloques de contenido de otra fuente dentro de su documento, agregue >antes de cualquier texto que desee citar.

```Markdown
> Donec massa lacus, ultricies a ullamcorper in, fermentum sed augue. Nunc augue augue, aliquam non hendrerit ac, commodo vel nisi.
>
> > Sed adipiscing elit vitae augue consectetur a gravida nunc vehicula. Donec auctor odio non est accumsan facilisis. Aliquam id turpis in dolor tincidunt mollis ac eu diam.
>
> Mauris sit amet ligula egestas, feugiat metus tincidunt, luctus libero. Donec congue finibus tempor. Vestibulum aliquet sollicitudin erat, ut aliquet purus posuere luctus.
```

> Donec massa lacus, ultricies a ullamcorper in, fermentum sed augue. Nunc augue augue, aliquam non hendrerit ac, commodo vel nisi.
>
> > Sed adipiscing elit vitae augue consectetur a gravida nunc vehicula. Donec auctor odio non est accumsan facilisis. Aliquam id turpis in dolor tincidunt mollis ac eu diam.
>
> Mauris sit amet ligula egestas, feugiat metus tincidunt, luctus libero. Donec congue finibus tempor. Vestibulum aliquet sollicitudin erat, ut aliquet purus posuere luctus.

## Enlaces 

##### Automático

```Markdown
Este es un enlace a https://www.ktm.com
```

Este es un enlace a https://www.ktm.com

##### Básico

```Markdown
[Ktm](https://www.ktm.com)
```
[Ktm](https://www.ktm.com)

##### Con información

Muestra un texto al pasar el cursor por encima del enlace
```Markdown
[Ktm](https://www.ktm.com "Pagina oficial")
```
[Ktm](https://www.ktm.com "Pagina oficial")

## Notas de pie de página

Las notas a pie de página funcionan principalmente como enlaces de estilo de referencia. Una nota al pie se compone de dos cosas: un marcador en el texto que se convertirá en un número en superíndice y una definición de nota al pie que se colocará en una lista de notas al pie.

That's some text with a footnote[^1]

[^1]: And that's the footnote.

That's some more text with a footnote.[^someid]

[^someid]:
    Anything of interest goes here.

    Blue light glows blue.



    
