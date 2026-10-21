# Prompts

---

## Prompt 1

**Modelo:** Opus 5.5 **Herramienta:** Claude Code **Tiempo**: 5m

```
Vamos a realizar una auditoria de la feature comentarios única y exclusivamente, obviando el resto de features.
Esto es una auditoria por lo tanto **NO DEBES** realizar modificaciones, borrado sobre ficheros o base de datos. Solamente 
consultas y análisis.
Audita la feature por completo, desde las rutas de la API, sus registros en tabla, lo que enseña en la web y lista los hallazgos.
Por definición, un hallazgo es una afirmación concreta que alguien puede ir a comprobar.
Cada hallazgo debe ser posible comprobarlo, si no se puede comprobar no es un hallazgo es una suposición.
Por cada hallazgo crea una tabla con 6 columnas que te paso a detallar:
- Que es? En un sola frase, si hay más de una son varios hallazgos
- Donde está? La linea que lo demuestra. Si no está, la linea no se escribe porque entra en contradicción con la definición de hallazgo
- Que se rompe, y quién lo nota. A quien le llega, si no llega a nadie o nadie lo nota, la respuesta "Nadie todavía" es correcta.
- Cuantos sitios hay que tocar. Contados reales, sin estimaciones
- ¿Se deshace con un revert? Si o no, en caso de ser un no, explica el motivo resumido
- ¿Bloquea o desbloquea otro hallazgo? Nombra a cual, en caso de negativo "A ninguno" es una respuesta correcta.
Si encuentras cualquier otro hallazgo que no se contemple en esta tabla, dejalo anotado al pie de la misma.
```

**Qué salió:** (opcional, una línea)  Mostró la tabla y datos complementarios a la auditoria requerida

## Prompt 2

**Auditoria adversarial con otro agente** **Modelo:** GPT 6.1 Sol **Herramienta:** Codex Tiempo: 3m

```markdown

Vamos a realizar una auditoria de la feature comentarios única y exclusivamente, obviando el resto de features.
Esto es una auditoria por lo tanto NO DEBES realizar modificaciones, borrado sobre ficheros o base de datos. Solamente
consultas y análisis.
Audita la feature por completo, desde las rutas de la API, sus registros en tabla, lo que enseña en la web y lista los hallazgos.
Por definición, un hallazgo es una afirmación concreta que alguien puede ir a comprobar.
Cada hallazgo debe ser posible comprobarlo, si no se puede comprobar no es un hallazgo es una suposición.
Por cada hallazgo crea una tabla con 6 columnas que te paso a detallar:
- Que es? En un sola frase, si hay más de una son varios hallazgos
- Donde está? La linea que lo demuestra. Si no está, la linea no se escribe porque entra en contradicción con la definición de hallazgo
- Que se rompe, y quién lo nota. A quien le llega, si no llega a nadie o nadie lo nota, la respuesta "Nadie todavía" es correcta.
- Cuantos sitios hay que tocar. Contados reales, sin estimaciones
- ¿Se deshace con un revert? Si o no, en caso de ser un no, explica el motivo resumido
- ¿Bloquea o desbloquea otro hallazgo? Nombra a cual, en caso de negativo "A ninguno" es una respuesta correcta.
  Si encuentras cualquier otro hallazgo que no se contemple en esta tabla, dejalo anotado al pie de la misma.

Esta auditoria comparala con tu propio criterio contra la actual, llamada comentarios.md dentro de la carpeta \wsl.localhost\Ubuntu\home\tony\repos\blog-legacy-ai4devs-202609-seniors-1\auditoria\comentarios.md y verifica si coincide o no con tus hallazgos.
```

**Qué salió:** (opcional, una línea)  Mostró la tabla y datos complementarios comparándola con la auditoria previa indicando que encontró 4 que no fueron detectados con Opus y reflejandolo en el documento como PATCH