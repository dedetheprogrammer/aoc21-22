# Arquitectura y organizacion de computadores 2
## [Proyecto 1](https://github.com/ddevigner/aoc21-22/tree/main/proyecto_1)
Implementación y ampliacion de un procesador MIPS de las siguientes características:
  - Segmentado a 5 ciclos:
    - Etapa **_FETCH_**: busqueda de la instrucción de la memoria de instrucción.
    - Etapa **_DECOD_**: decodificación de la instrucción y obtención de datos del banco de registros.
    - Etapa **_EXECUTION_**: operación de ALU.
    - Etapa **_MEMORY_**: acceso a memoria.
    - Etapa **_WRITE BACK_**: escritura a banco de registros.
  - Instruction-set original: _ADD_, _BEQ_, _LW_, _SW_ y _NOP_.
  - Implementación de _ruta de datos para operaciones en coma flotante_ y ampliación del instruction-set: ADDFP, LWFP, SWFP.
  - Implementación de una _Unidad de anticipación_ para dependencia de datos.
  - Implementación de una _Unidad de detección_ para la detección de riesgos:
    - **Depedencia de datos**: si una instruccion beq requiere de un dato, el procesador deberá parar hasta poder leer el dato.
    - **Riesgo LD-USO**: una instrucción requiere de un dato de memoria que no se puede anticipar.
    - **Riesgos de control**: un salto no puede determinarse hasta etapa Decod, por lo que siempre entrará una instrucción al pipeline.
    - **Riesgos estructurales**: una operación en coma flotante tiene variada duración, por lo inutiliza la ruta de datos para el restro de instrucciones.

## [Fast-MIPS](https://github.com/ddevigner/aoc2-21-22/tree/main/fast-mips)
Programa que traduce un programa ensamblador MIPS (Proyecto 1), codifica las instrucciones y las parsea en formato RAM de VHDL.
- Ubicado en la carpeta [fast-mips/dist/](https://github.com/ddevigner/aoc2-21-22/tree/main/fast-mips/dist)[fast-mips.exe](https://github.com/ddevigner/aoc2-21-22/blob/main/fast-mips/dist/fast-mips.exe)
- Utilizacion
```bash
  fast-mips <file>
```
