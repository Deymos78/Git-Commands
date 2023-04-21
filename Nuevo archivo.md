Probando el nuevo archivo

# SUPERTITULO
 
## Titulo

### Subtitulo

Este es un ejemplo de texto que da entrada a una lista generica de elementos:

- Elemento 1

- Elemento 2

- Elemento 3

Este es un ejemplo de texto que da entrada a una lista numerada

1. Elemento 1

2. Elemento 2

3. Elemento 3

Otro ejemplo de lista

* Elemento 1

* Elemento 2

* Elemento 3

___

Aqui va otro elemento de lista ejemplo

+ Elemento 1

+ Elemento 2

+ Elemento 3

---


Aqui viene un ejemplo de listas anidadas

- Elemento de la lista 1

- Elemento de la lista 2

	- Supuesto elemento anidado 1
	
	- Supuesto elemento anidado 2
	
		- Supuesto elemento super anidado 1
		
		- Supuesto elemento super anidado 2

Al texto en Markdown puedes añadirle formato como **negrita** o *cursiva* de una manera muy sencilla1


> Esta es una cita de una civilizacion antigua. -Tu madre

***


Ahora crearemos codigo encapsulado

~~~

export const getGifs = async(category) => {

    const url = `https://api.giphy.com/v1/gifs/search?api_key=F95hkGLnz2unWMtwvFv3rIlLkTLFDkh1&q=${ category }&limit=10`
    
    const resp =  await fetch( url );
    
    const { data } = await resp.json();

    const gifs = data.map( img => ({
        id: img.id,
        title: img.title,
        url: img.images.downsized_medium.url
    }));

    return gifs;
}
~~~ 


Ahora se veran links, se usan corchetes '[]' y el link en cuestion en "()" parentesis

**Enlace a pagina web WindBlatt3d**


[pagina web modelos 3d](https://windblatt3d.com/)

Ahora colocaremos una linea de codigo

Esta es una linea de codigo la siguiente `console.log('Nueva caractetistica')`



















