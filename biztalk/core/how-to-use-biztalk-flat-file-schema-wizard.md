---
title: Cómo usar el Asistente para esquemas de archivo sin formato de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7cb8b18-266d-422e-bdb8-1efefb6b4c8e
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3118e66658eb8bf23f805c1055d69ba6164af26e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975981"
---
# <a name="how-to-use-biztalk-flat-file-schema-wizard"></a>Cómo utilizar el Asistente para esquemas de archivo sin formato de BizTalk
En versiones anteriores de BizTalk Server había que agregar manualmente las anotaciones en los esquemas del lenguaje de definición de esquemas XML (XSD) en el Editor de esquema de BizTalk para que los esquemas fueran comprensibles para los componentes de canalización de archivos sin formato, como el Desensamblador de archivo sin formato y el Ensamblador de archivo sin formato. Puede seguir haciéndolo con el editor de esquemas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para reducir el número de pasos manuales, así como el tiempo necesario para crear soluciones, utilice el Asistente para esquemas de archivos sin formato de BizTalk, que ofrece las funciones siguientes:  
  
-   Utiliza instancias de archivo sin formato real como entrada.  
  
-   Incluye una superficie de diseño visual para trabajar con esquemas de archivo sin formato delimitado y posicional.  
  
-   Utiliza un proceso reentrante basado en asistentes para agregar elementos al esquema y definir anotaciones relacionadas con los archivos sin formato de forma interactiva.  
  
-   Proporciona compatibilidad para los identificadores de etiquetas y los delimitadores hexadecimales y de caracteres.  
  
-   Determina automáticamente los desplazamientos de identificadores de etiquetas y el orden de delimitación del elemento secundario.  
  
-   Ofrece funciones de vista previa para el formato del archivo.  
  
-   Permite seleccionar los datos secundarios dentro de la instancia de intercambio que se va a utilizar para definir los esquemas de archivos sin formato.  
  
## <a name="how-to-start-the-biztalk-flat-file-schema-wizard"></a>Cómo iniciar el Asistente para esquemas de archivos sin formato de BizTalk  
 Puede iniciar el asistente desde el Explorador de soluciones de Microsoft Visual Studio o desde el Editor de esquema de BizTalk.  
  
#### <a name="to-start-the-wizard-from-solution-explorer"></a>Para iniciar el asistente desde el Explorador de soluciones  
  
1. En Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el **el Explorador de soluciones**.  
  
2. Para agregar el nuevo esquema de archivo sin formato, haga clic en el proyecto de BizTalk y seleccione **agregar**.  
  
3. Haga clic en **nuevo elemento.**  
  
    ![Menú Explorador de soluciones](../core/media/flatfileschemawizard-01.gif "FlatFileSchemaWizard_01")  
  
4. En el **Agregar nuevo elemento** ventana, haga lo siguiente:  
  
   1.  En el **categorías** sección, seleccione **archivos de esquema**.  
  
   2.  En el **plantillas** sección, seleccione **Asistente para esquemas de archivo sin formato**.  
  
   3.  En el **nombre** cuadro de texto, escriba un nombre para el nuevo esquema.  
  
   4.  Haga clic en **Agregar**.  
  
        Se abre el Asistente para esquema de archivo sin formato de BizTalk  
  
#### <a name="to-start-the-wizard-from-the-schema-editor"></a>Para iniciar el asistente desde el Editor de esquema  
  
1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el **el Explorador de soluciones**.  
  
2. Para agregar el nuevo esquema de archivo sin formato, haga clic en el proyecto de BizTalk y seleccione **agregar**. Seleccione **nuevo elemento** y haga clic en **nuevo elemento**.  
  
3. En el **Agregar nuevo elemento** ventana, haga lo siguiente:  
  
   1.  En el **categorías** sección, seleccione **archivos de esquema**.  
  
   2.  En el **plantillas** sección, seleccione **esquema de archivo sin formato**.  
  
   3.  En el **nombre** cuadro de texto, escriba un nombre para el nuevo esquema.  
  
   4.  Haga clic en **Agregar**.  
  
   5.  Haga clic en **raíz** y seleccione **definir registro desde instancia de archivo sin formato**.  
  
        Ahora se inicia el Asistente para esquemas de archivos sin formato de BizTalk.  
  
> [!NOTE]
>  Si tiene un esquema en funcionamiento abierto en el Editor de esquemas, todo lo que necesita hacer es haga clic en el nodo seleccionado y, a continuación, seleccione **definir registro desde instancia de archivo sin formato**.  
  
> [!NOTE]
>  El **definir registro desde instancia de archivo sin formato** opción está habilitada si el nodo seleccionado es un registro sin elementos secundarios. Si el nodo seleccionado tiene elementos secundarios, el asistente elimina todos los elementos secundarios actuales y genera los nuevos. El asistente le solicita que confirme la eliminación de los elementos secundarios existentes.  
  
## <a name="considerations-for-using-the-flat-file-schema-wizard"></a>Consideraciones sobre el uso del Asistente para esquemas de archivos sin formato  
 En esta sección se describen los aspectos que debería tener en cuenta al trabajar con el Asistente para esquemas de archivos sin formato de BizTalk.  
  
### <a name="working-with-multibyte-character-set-mbcs"></a>Trabajar con juegos de caracteres multibyte (MBCS)  
 De forma predeterminada, el **contar posiciones en bytes** casilla de verificación está desactivada en la pantalla de información de esquema de archivo sin formato. El asistente cuenta las posiciones por caracteres, lo que significa que si tiene caracteres MBCS en la instancia de archivo sin formato posicional, las posiciones no se contarán correctamente. Si selecciona el **contar posiciones en bytes** casilla de verificación, el asistente muestra caracteres MBCS con una indicación adicional de su longitud posicional. El carácter toma una posición en la pantalla y se rellena la longitud restante con símbolos de punto " •". El número de símbolos de punto rellenos dependerá de los archivos que se guardaran en el juego de caracteres de doble byte, formato Unicode o UTF-8.  
  
### <a name="code-pages-supported-in-the-flat-file-schema-wizard"></a>Páginas de códigos compatibles en el Asistente para esquemas de archivos sin formato  
 A continuación, se muestra una lista de las páginas de códigos compatibles del asistente:  
  
-   Árabe (1256)  
  
-   ASCII (20127)  
  
-   Báltico (1257)  
  
-   Big-Endian-UTF16 (1201)  
  
-   Central europea (1250)  
  
-   Cirílico (1251)  
  
-   Griego (1253)  
  
-   Hebreo (1255)  
  
-   Japonés Shift_JIS (932)  
  
-   Coreano (949)  
  
-   Little-Endian-UTF16 (1200)  
  
-   Chino-simplificado-GBK (936)  
  
-   Chino-simplificado-GB18030 (54936)  
  
-   Tailandés (874)  
  
-   Chino-tradicional-BIG5 (950)  
  
-   Turco (1254)  
  
-   UTF-7 (65000)  
  
-   UTF-8 (65001)  
  
-   Vietnamita (1258)  
  
-   Europeo occidental (1252)  
  
### <a name="record-types-in-the-flat-file-schema-wizard"></a>Tipos de registro del esquema Asistente de esquemas de archivos sin formato  
 Los archivos sin formato no pueden contener registros delimitados dentro de registros posicionales. Dado que el asistente es reentrante basado, los botones de radio que definen el tipo de la **por símbolo delimitador** y **por posiciones relativas** se habilitan o deshabilitan según el formato de los registros primarios para el elemento secundario que se define en el asistente. Por ejemplo,  
  
-   Si se ejecuta el asistente en un elemento secundario de un registro delimitado, se seleccionan los dos botones de opción.  
  
-   Si se ejecuta el Asistente para un elemento secundario de un registro posicional, el **por símbolo delimitador** botón de radio está desactivada.  
  
### <a name="delimiter-symbols-in-the-flat-file-schema-wizard"></a>Símbolos delimitadores del Asistente de esquemas de archivos sin formato  
 La lista desplegable de propiedades del delimitador secundario contiene los siguientes delimitadores comunes:  
  
- {CR}{LF}  
  
- {CR}  
  
- {LF}  
  
- {TAB}  
  
- {SPACE}  
  
- {0x1A}  
  
- &#124;  
  
- ,  
  
- ;  
  
  El valor predeterminado de esta propiedad es {CR}{LF}. La propiedad también es un cuadro de texto editable, por lo que puede especificar el delimitador secundario como una secuencia de caracteres o como valores hexadecimales de los caracteres. Un ejemplo del uso de caracteres del delimitador secundario sería "una" o "calle". Los delimitadores hexadecimales se especifican con el formato siguiente:  
  
- {0xnnnn}. Por ejemplo, {0x0D} {0x0A}, {0 x 09} o {0 x 20}.  
  
  Un ejemplo del uso de la secuencia de valores hexadecimales es {0x0D}{0x0A}, {0x09}{0x20}.  
  
  Si utiliza los símbolos \\, {, o} como delimitador, debe colocar un símbolo de barra diagonal inversa adicional delante del símbolo delimitador, en caso contrario, recibirá un mensaje de error. Por ejemplo,  
  
- \\\\, \\{, o \\}.  
  
### <a name="relative-positions-in-the-flat-file-schema-wizard"></a>Posiciones relativas en el Asistente de esquemas de archivos sin formato  
  
#### <a name="setting-position-markers"></a>Establecimiento de marcadores de posición  
 Use el botón primario del mouse para hacer clic en un marcador de posición en el cuadro de selección de posición para establecer la nueva línea del marcador de posición. El marcador de posición se representa como una línea continua. De forma predeterminada, existe una línea de marcador de posición al principio del registro en la posición cero. Para quitar una línea de marcador de posición existente, haga clic en ella con el botón primario del mouse.  
  
### <a name="escape-characters-in-the-flat-file-schema-wizard"></a>Caracteres de escape del Asistente de esquemas de archivos sin formato  
 Un carácter de escape es un carácter individual que suprime cualquier significado especial que tenga el carácter que le sigue. Para obtener más información, consulte [caracteres de Escape](../core/escape-characters.md) tema [formas de interpretar los caracteres especiales como parte de un valor de campo](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md). Utiliza la propiedad de carácter de escape en el asistente para determinar el carácter de escape que se va a utilizar al analizar la instancia de archivo sin formato. El valor predeterminado es nulo, lo que significa que se utiliza el carácter de escape predeterminado definido en el nivel de esquema.  
  
 El carácter de escape se puede definir como un carácter o como un valor hexadecimal. El valor hexadecimal se especifica con el formato siguiente:  
  
- {0xnnnn}. Por ejemplo: {0x0D}{0x0A}, {0x09} o {0x20}.  
  
  Si utiliza los símbolos \\, {, o} como carácter de escape, debe colocar un símbolo de barra diagonal inversa adicional delante del símbolo delimitador, en caso contrario, recibirá un mensaje de error, por ejemplo,  
  
- \\\\, \\{, \\}.  
  
### <a name="child-elements-in-the-flat-file-schema-wizard"></a>Elementos secundarios del Asistente para esquema de archivo sin formato  
 Cada elemento secundario contiene **nombre del elemento**, **tipo de elemento**, **tipo de datos** y **contenido**. Usa el **nombre del elemento** cuadro de texto para escribir un nombre descriptivo para el nodo. El **tipo de elemento** es una lista desplegable con los valores siguientes:  
  
- **Elemento de campo**: Especifica que este nodo se creará en el esquema como un elemento.  
  
- **Atributo de campo**: Especifica que este nodo se creará en el esquema como un atributo.  
  
- **Registro**: Especifica que se creará un registro sin elementos secundarios en el esquema.  
  
- **Repitiendo registro**: Especifica que se creará un registro sin elementos secundarios en el esquema y sus repeticiones máximas se establecen en **Unbounded**.  
  
- **Omitir**: se creará nada en el esquema para este nodo.  
  
  De forma predeterminada, todos los elementos son de tipo **elemento de campo** y su tipo de datos es **cadena**.  
  
> [!NOTE]
>  Un elemento secundario se puede declarar como una **atributo de campo** solo si no hay ningún elemento secundario antes de que se declaran como **campo elementos**, **registro** o  **Repitiendo registro**.  
  
> [!NOTE]
>  Verá una marca de exclamación delante de la **nodos secundarios** en los casos siguientes:  
  
-   El **atributo de campo** se define después **elemento de campo**, **registro,** o **repitiendo registro**.  
  
-   El elemento secundario no tiene nombre.  
  
-   El elemento secundario tiene un nombre duplicado.  
  
-   El tipo de datos seleccionado para el elemento secundario no resulta adecuado para el contenido.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial del Asistente para esquemas de archivo sin formato de BizTalk](../core/biztalk-flat-file-schema-wizard-walkthrough.md)