---
title: Implementar el ejemplo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd788fd3-b070-40d5-a3d3-ac8e5208cc47
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6622d201c6f7b7d94694a77198d0eb562482489
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="implementing-the-sample"></a>Implementar el ejemplo
Para implementar el ejemplo, haga lo siguiente:  
  
1.  Crear una nueva carpeta para SWIFT esquemas (\<DocumentSchemaLocation\> en la sintaxis de la utilidad). Todos los esquemas para los que se va a crear o modificar los formularios de InfoPath deben encontrarse en esta carpeta cuando se ejecuta la utilidad.  
  
2.  Si va a generar los formularios de InfoPath para los mensajes de MT, a continuación, copie **SWIFT Base Types.xsd** y **Types.xsd de datos común de SWIFT** de  **\<unidad:\> \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión del módulo de mensaje\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión del módulo de mensaje\>\Base esquemas** en la carpeta que crea esquemas SWIFT.  
  
3.  Copie todos los esquemas para los que va a crear los formularios de InfoPath en la carpeta que ha creado para SWIFT esquemas en el paso 1.  
  
4.  Cree o designe una carpeta que contiene el formulario de InfoPath creado los archivos de solución de plantilla (\<DestinationFolderPath\> en la sintaxis de la utilidad). Si no crea la carpeta de salida, la utilidad creará la misma con la ruta de acceso y el nombre que pasa en la línea de comandos.  
  
5.  [Opcional]-crear un archivo de texto \<NameOfFileContainingSchemaList\> que enumeran los tipos de mensaje para los mensajes para los que es el formulario de InfoPath que se genere. Por ejemplo, el tipo de mensaje puede ser MT103, MT102 etcetera. Los nombres de mensaje pueden pasarse directamente a través de la línea de comandos en lugar de crear este archivo de texto.  
  
## <a name="syntax-of-command-usage-for-formgeneratorexe"></a>Sintaxis de uso del comando para FormGenerator.exe  
  
```csharp  
FormGenerator [-b]   [-#] <TemplateFolderPath> [<TemplateFolderPath2>   
   [...<TemplateFolderPath#>]]  
 <DestinationFolderPath>     <DocumentSchemaLocation>  
   { [<SpaceSeparatedDocumentSchemaList>] |   [-f <NameOfFileContainingSchemaList>] }  
  
```  
  
 Donde:  
  
-   -b: si se especifica, se compilará forms después de su creación.  
  
-   TemplateFolderPath: la carpeta que contiene los archivos de plantilla utilizados para crear la solución de InfoPath  
  
-   -#: Si se especifica, las plantillas se buscará en varias rutas de acceso de plantilla (tantos como el entero especifica número #) y en el orden especificado.  
  
-   DestinationFolderPath: la carpeta donde se creará los formularios  
  
-   DocumentSchemaLocation: ubicación de esquemas (incluidos los esquemas de base y comunes para los mensajes de MT)  
  
-   SpaceSeparatedDocumentSchemaList: lista separada por espacios de esquemas como MT103 MT300.  
  
-   -f: si se especifica, la lista de esquemas tiene que leerse desde un archivo.  
  
-   NameOfFileContainingSchemaList: el nombre del archivo que contiene la lista.  
  
    > [!NOTE]
    >  El comando anterior es un comando genérico para MT, MX y categoría 0 mensajes. Comandos específicos para generar estos tipos de formularios se proporcionan en el siguiente secciones.