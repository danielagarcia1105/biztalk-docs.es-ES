---
title: Functoid personalizado (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids, customizing
- examples, functoids
- functoids, examples
- XML tools
- examples, XML tools
ms.assetid: 9f1eb260-ff62-46f5-a517-57f4e9172b35
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de71eb45faa6c5705cca2ef47061686608126577
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013395"
---
# <a name="custom-functoid-biztalk-server-sample"></a>Functoid personalizado (ejemplo de BizTalk Server)
El ejemplo de functoid personalizado muestra cómo escribir un functoid personalizado para el asignador de BizTalk. Puede agregar el functoid al cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. El functoid se mostrará en el cuadro de herramientas cuando el asignador de BizTalk esté en el foco.  
  
 Un functoid personalizado debe residir en un ensamblado del asignador de BizTalk para reconocerlo. Puede escribirse en cualquier lenguaje compatible con .NET, como C# o Visual Basic.  
  
 Asimismo, un functoid personalizado debe derivarse de la clase `Microsoft.BizTalk.BaseFunctoids` y debe proporcionar implementación para algunos métodos mediante su anulación. (La clase `BaseFunctoid` se define en el ensamblado Microsoft.BizTalk.BaseFunctoids.dll incluido con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 El ejemplo de functoid personalizado implementa varios functoids, cada uno se deriva de la clase `BaseFunctoid` y anula varios métodos.  
  
 Al implementar un functoid personalizado, puede exponer su código interno. El código interno es el que lleva a cabo el cálculo del functoid. El compilador del asignador de BizTalk extrae el código interno y los integra en el XSLT compilado cuando se genera el proyecto.  
  
 Si el functoid personalizado no expone ningún código interno, el asignador de BizTalk genera un XSLT que llama al ensamblado en el que reside el functoid personalizado. En este caso, debe asegurarse de que el ensamblado del functoid personalizado está disponible en la caché de ensamblados global (GAC) para que el motor de XSLT pueda encontrarla. Un functoid personalizado también debe tener un atributo de GUID único. El asignador de BizTalk utiliza el GUID para identificar qué ensamblado cargar.  
  
> [!IMPORTANT]
>  Si reutiliza el código de ejemplo del functoid personalizado para implementar su propio functoid, debe asegurarse de cambiar el atributo de GUID a uno que sea único.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de la ruta de acceso\>* \XmlTools\CustomFunctoid  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Descripción|  
|---------------|-----------------|  
|AssemblyInfo.cs|Código de origen de C# de información de ensamblado.|  
|CBuildArray.bmp|Mapa de bits del cuadro de herramientas.|  
|CConcat.bmp|Mapa de bits del cuadro de herramientas.|  
|CExtractArray.bmp|Mapa de bits del cuadro de herramientas.|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y eliminarlos de la caché de ensamblados global (GAC), así como para eliminar CustomFunctoid.dll.|  
|CLongestString.bmp|Mapa de bits del cuadro de herramientas.|  
|CMultiply.bmp|Mapa de bits del cuadro de herramientas.|  
|CustomFunctoid.cs|Código de origen de C# del functoid personalizado.|  
|CustomFunctoid.csproj|Proyecto de C# del functoid personalizado.|  
|CustomFunctoid.sln|Solución de functoid personalizado.|  
|CustomFunctoidResources.resx|Recursos del functoid personalizado.|  
|Setup.bat|Se utiliza para generar, implementar e iniciar el ejemplo.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 Utilice el siguiente procedimiento para crear e inicializar el ejemplo del functoid personalizado.  
  
#### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En una ventana de comandos, cambie el directorio (**cd**) a la siguiente carpeta:  
  
     \<*Ejemplos de la ruta de acceso*\>\XmlTools\CustomFunctoid  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Genera el proyecto de ejemplo.  
  
    -   Copia el ensamblado generado en el directorio Herramientas de programador\Extensiones de asignador.  
  
    -   Agrega el ensamblado generado en la GAC.  
  
        > [!NOTE]
        >  Debe confirmar que no se ha informado de errores durante el proceso de creación e iniciación antes de intentar ejecutar este ejemplo.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo del functoid personalizado.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1. Desde un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, haga clic en el **herramientas** menú y seleccione **elegir elementos del cuadro de herramientas**.  
  
2. En el **elementos del cuadro de herramientas elija** cuadro de diálogo, seleccione el **Functoids del asignador de BizTalk** ficha.  
  
3. Haga clic en **restablecer**y, a continuación, haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  Si su functoid personalizado no expone ningún código en línea, asegúrese de que su ensamblado está disponible en la caché de ensamblados global.  
  
4. Desde el **archivo** menú, seleccione **Exit** para cerrar [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
5. Iniciar **símbolo del sistema de Visual Studio**.  
  
6. En el símbolo del sistema, escriba **devenv /setup**.  
  
7. Iniciar **Microsoft Visual Studio**.  
  
    Personalizado functoids (functoid de concatenación personalizada, cadena más larga, el functoid de matriz de compilación y el functoid de extracción de matriz) aparecen en la **Functoids de cadena** ficha del cuadro de herramientas y el functoid de multiplicación acumulada aparece en el **Functoids acumulativos** ficha.  
  
## <a name="removing-this-sample"></a>Eliminar este ejemplo  
 Utilice el siguiente procedimiento para eliminar el ejemplo del functoid personalizado.  
  
#### <a name="to-remove-this-sample"></a>Para quitar este ejemplo  
  
1. Quite los functoids del cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
   > [!WARNING]
   >  Si, después de ejecutar Cleanup.bat, sigue viendo los functoids personalizados obsoletos en el cuadro de herramientas (probablemente debido a la memoria caché interna de Visual Studio), siga los procedimientos siguientes:  
  
   1. Desde un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, haga clic en el **herramientas** menú y seleccione **elegir elementos del cuadro de herramientas**.  
  
   2. En el **elementos del cuadro de herramientas elija** cuadro de diálogo, seleccione el **Functoids del asignador de BizTalk** ficha.  
  
   3. Busque en la lista los functoids personalizados (de concatenación personalizada, de cadena más larga, de generación de matriz, de extracción de matriz y de multiplicación acumulada). Haga clic en los respectivos **casilla** para quitar los functoids y, a continuación, haga clic en **Aceptar**.  
  
      Si no funciona el procedimiento anterior, siga el procedimiento siguiente.  
  
   4. Desde el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, haga clic en el **cuadro de herramientas** ficha mientras edita una asignación para abrir la paleta de cuadro de herramientas.  
  
   5. Haga clic en el cuadro de herramientas y seleccione **elegir elementos**.  
  
   6. En el cuadro de diálogo Elegir elementos, haga clic en **restablecer**y, a continuación, haga clic en **Aceptar**.  
  
   7. Cierre todas las instancias de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
      Si no funciona el procedimiento anterior, siga el procedimiento siguiente.  
  
   8. Iniciar **Visual Studio Command Prompt** como administrador.  
  
   9. Cierre todas las instancias en ejecución de Visual Studio.  
  
   10. Escriba los comandos siguientes:  
  
        `devenv /resetsettings`  
  
        `devenv /setup`  
  
   11. Puede seleccionar manualmente los functoids no deseados en el cuadro de herramientas. A continuación, haga clic con el botón secundario del mouse en el functoid y haga clic en **eliminar**.  
  
       Si no funciona el procedimiento anterior, siga el procedimiento siguiente.  
  
   12. En un proyecto de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], haga clic en la pestaña Cuadro de herramientas mientras edita una asignación para abrir la paleta de cuadro de herramientas.  
  
   13. Haga clic en el **Functoids acumulativos** grupo.  
  
   14. Haga clic con el botón secundario del mouse en el functoid que desea quitar y, a continuación, elija **eliminar** o presione la tecla SUPR.  
  
   15. Haga clic en el **Functoids de cadena** grupo.  
  
   16. Haga clic con el botón secundario del mouse en el functoid que desea quitar y, a continuación, elija **eliminar** o presione la tecla SUPR.  
  
2. En una ventana de comandos, cambie el directorio (**cd**) a la siguiente carpeta:  
  
    \<*Ejemplos de la ruta de acceso*\>\XmlTools\CustomFunctoid  
  
3. Ejecute el archivo Cleanup.bat que realiza las acciones siguientes:  
  
   -   Elimina el ensamblado del directorio Herramientas de programador\Extensiones de asignador.  
  
   -   Elimina el ensamblado de la GAC.  
  
## <a name="classes-or-methods-used-in-this-sample"></a>Clases o métodos usados en el ejemplo  
 [Microsoft.BizTalk.BaseFunctoids.BaseFunctoid](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.basefunctoid.aspx)  
  
## <a name="see-also"></a>Vea también  
 [Uso de BaseFunctoid](../core/using-basefunctoid.md)   
 [Herramientas XML (carpeta de ejemplos de BizTalk Server)](../core/xml-tools-biztalk-server-samples-folder.md)