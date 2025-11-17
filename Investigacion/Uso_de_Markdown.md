# Documentación: Markdown en Proyectos de Software

## ¿Qué es Markdown y por qué se utiliza en proyectos de software?

### Definición
Markdown es un lenguaje de marcado ligero creado por John Gruber en 2004. Utiliza una sintaxis simple y fácil de aprender que se convierte a HTML válido. Su objetivo principal es permitir a los escritores crear contenido que sea legible tanto en su forma original como cuando está convertido.

### Por qué se usa en proyectos de software

**Legibilidad y Simplicidad**
- Sintaxis intuitiva que no requiere conocimientos técnicos avanzados
- Archivos de texto plano que son fáciles de versionar
- Se puede leer y editar en cualquier editor de texto

**Estandarización de Documentación**
- README.md como punto de entrada estándar en repositorios
- Documentación consistente across diferentes proyectos
- Fácil mantenimiento y actualización

**Integración con Herramientas de Desarrollo**
- Compatibilidad nativa con GitHub, GitLab, Bitbucket
- Renderizado en IDEs y editores de código
- Soporte en sistemas de CI/CD

**Colaboración Efectiva**
- Merge conflicts fáciles de resolver comparado con formatos binarios
- Revisiones de código más claras
- Comentarios y discusiones basadas en texto

## Ejemplo Práctico de Uso de Markdown

## Encabezados
### Se crean usando el simbolo # y mientras mas # uses mas pequeña será la letra
```
# Encabezado 1 
## Encabezado 2 
### Encabezado 3 
#### Encabezado 4 
##### Encabezado 5
###### Encabezado 6
```
## Listas
### Lista no ordenada 
### Se puede usar esta variedad de símbolos * - + dejando un espacio entre el símbolo y el texto
```
- Elemento de lista 1
- Elemento de lista 2
  - Subelemento 2.1
  - Subelemento 2.2
```
### Lista ordenada 
### Se debe anteponer un numero seguido del punto y a continuacion dejar un espacio para despues escribir el texto 
```
1. Primer elemento
2. Segundo elemento
3. Tercer elemento
```
## Tablas 
### Se puede usar este simbolo  | junto a los guiones para estructurar mejor el texto
```
| Columna 1 | Columna 2 | Columna 3 |
|-----------|-----------|-----------|
| Dato A1   | Dato A2   | Dato A3   |
| Dato B1   | Dato B2   | Dato B3   |
| Dato C1   | Dato C2   | Dato C3   |
```
### Tambien puedes usar otras herramientas como html
```
<table>
  <thead>
    <tr>
      <th>Columna 1</th>
      <th>Columna 2</th>
      <th>Columna 3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Dato A1</td>
      <td>Dato A2</td>
      <td>Dato A3</td>
    </tr>
    <tr>
      <td>Dato B1</td>
      <td>Dato B2</td>
      <td>Dato B3</td>
    </tr>
  </tbody>
</table>
```
## Enlaces
### Para crear un link debemos seguir la estructura []() Entre parentesis ponemos el texto que se visualizará y entre corchetes el link
```
[]()
[Texto del enlace](https://ejemplo.com)
[Enlace con título](https://ejemplo.com "Título del enlace")
```
## Imagenes
### Es muy parecida a la estructura de un enlace pero debemos iniciar con el símbolo !. Entre parentesis ponemos una referencia a la imagen y entre los corchetes el texto alternativo 
```
![]()
![Foto](ruta/a/la/imagen.jpg)
```
Markdown y GitHub forman una combinación muy útil para la documentación de proyectos. GitHub renderiza automáticamente los archivos .md, haciendo que READMEs, wikis y páginas de proyecto sean visualmente atractivas y fáciles de navegar. La plataforma extiende Markdown con funciones exclusivas como listas de tareas interactivas, mención de usuarios, referencia a issues y tablas avanzadas.

Los archivos Markdown se integran perfectamente con el control de versiones de Git, permitiendo trackear cambios en la documentación igual que en el código. GitHub Actions puede validar y desplegar automáticamente la documentación, mientras que los badges muestran el estado del proyecto en tiempo real.

Esta integración favorece la colaboración mediante pull requests con descripciones formateadas, issues organizados y comentarios precisos. El resultado es una documentación siempre actualizada, accesible desde cualquier dispositivo y que evoluciona junto con el código del proyecto.






