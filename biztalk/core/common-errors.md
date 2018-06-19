---
title: Errores comunes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fe48a8e-def0-4a00-aa7f-9a49ae555351
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b882c44e69489114a2dd8084df71d6414df0cb5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971538"
---
# <a name="common-errors"></a>Errores comunes
En este tema se muestran mensajes de error habituales que pueden aparecer al crear asignaciones usando el Asignador de BizTalk.  
  
## <a name="you-receive-error-event-id-324-when-parsing-dates"></a>Recibe el evento de error ID 324 al analizar las fechas  
  
### <a name="problem"></a>Problema  
 Cuando se usa la base de datos **Extractor de valor** functoid en una asignación para extraer un campo de fecha, el documento puede producir un error de validación en la definición de documento de salida. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]puede registrar un error de validación similar al siguiente en el registro de eventos:  
  
 Origen del evento: El servidor BizTalk Server  
  
 Categoría del evento: Procesamiento de documentos de  
  
 Id. de evento: 324  
  
 Descripción:  
  
 Error en el servidor BizTalk Server.  
  
 Detalles:  
  
 -----------------------------\-  
  
 El documento XML no pudo validar por el siguiente motivo: Error al analizar ' 10/12/1995 ' como tipo de datos de fecha.  
  
 Id. de cola de suspensión: "{A1127909-CA36-4359-B672-7CBA8B60BDAF}"  
  
### <a name="cause"></a>Causa  
 El formato de fecha (como se devuelve del origen de datos) no está en formato ISO 8601, que es el formato que XML necesita.  
  
### <a name="resolution"></a>Solución  
 Para resolver este problema, realice una de las siguientes opciones:  
  
-   Edite la definición del documento de salida para usar un tipo de datos de cadena en vez de un tipo de datos de fecha.  
  
-   Crear una personalizada [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)] **Script** functoid que convierta el resultado de la base de datos **Extractor de valor** functoid en el formato ISO 8601.  
  
 Para obtener más información, consulte el artículo de KB [278737](http://support.microsoft.com/kb/278737/en-us).  
  
## <a name="you-receive-internal-compiler-error-0xc0000005-at-address-53624fd6-when-compiling-the-maps"></a>Recibe un error del compilador interno (0xc0000005 en la dirección 53624FD6) al compilar las asignaciones  
  
### <a name="problem"></a>Problema  
 Al compilar un único proyecto de BizTalk que consta de esquemas, asignaciones u orquestaciones de gran tamaño, el compilador puede generar un error parecido al siguiente:  
  
 Error interno del compilador (0xc0000005 en la dirección 53624FD6): probablemente la causa sea 'CODEGEN'.  
  
### <a name="cause"></a>Causa  
 El compilador de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] tiene un límite de 16 megabytes en el tamaño total de todas las cadenas en un único proyecto. Al compilar proyectos de BizTalk, el compilador serializa esquemas, asignaciones y orquestaciones para crear los ensamblados y, por ello, el tamaño total de todas las cadenas aumenta y puede superar el límite.  
  
### <a name="resolution"></a>Solución  
 Para resolver este problema, puede separar esquemas o asignaciones en varios proyectos de BizTalk.  
  
## <a name="you-receive-errors-about-the-type-name-of-a-biztalk-artifact"></a>Recibe errores sobre el nombre de tipo de un artefacto de BizTalk  
  
### <a name="problem"></a>Problema  
 En un proyecto de BizTalk, cree un mapa con nombre de archivo **System.btm** o **Microsoft.btm**. Al generar el proyecto, el Asignador de BizTalk genera un error similar a alguno de los siguientes:  
  
-   “El nombre de tipo ‘SerializableAttribute’ no existe…”  
  
-   “El nombre de tipo ‘NonSerializableAttribute’ no existe…”  
  
-   “El nombre de tipo ‘SerializableAttributeAttribute’ no existe…”  
  
-   “El nombre de tipo ‘XLANs’ no existe…”  
  
### <a name="cause"></a>Causa  
 El **nombre de tipo** en el **propiedades** cuadrícula no debe tener los espacios de nombres .NET reservado, como **System**, **Microsoft**, etcetera.  
  
### <a name="resolution"></a>Solución  
 Para resolver este problema, puede seguir cualquiera de estas soluciones:  
  
-   Modifique el nombre de la asignación por cualquier cadena que no sea una palabra reservada de .NET. De forma predeterminada, el sistema de proyectos de BizTalk crea el **nombre de tipo** desde el nombre del artefacto respectivo.  
  
     Para p. ej.: crear una nueva asignación con el nombre **Map1.btm** establece la **nombre de tipo** valor de propiedad **Map1**. Sin embargo, cambiar el nombre de un BizTalk existente artefacto no cambia la **nombre de tipo**.  
  
-   Asegúrese de que el nombre de archivo de cualquiera de los artefactos del proyecto BizTalk no es un espacio de nombres reservado de .NET.  
  
## <a name="you-receive-errors-about-the-file-name-of-a-biztalk-artifact"></a>Recibe errores sobre el nombre de archivo de un artefacto de BizTalk  
  
### <a name="problem"></a>Problema  
 Al generar un proyecto de BizTalk, el Asignador de BizTalk genera un error similar a alguno de los siguientes:  
  
-   "El archivo \<filename\> tiene valores duplicados para las propiedades de nombre de espacio de nombres y tipo."  
  
-   "El espacio de nombres \<nombre\> ya contiene una definición para '_'."  
  
### <a name="cause"></a>Causa  
 En el proyecto de BizTalk, compruebe lo siguiente:  
  
-   Varios artefactos tienen el mismo nombre de archivo. Para p. ej., **Map1.xsd** y**Map1.btm**.  
  
-   El nombre de archivo consta únicamente de caracteres especiales (**~**, **!**,  **@** , etcetera.).  
  
### <a name="resolution"></a>Solución  
 Para resolver este problema, puede seguir cualquiera de estas soluciones:  
  
-   Cambie el nombre de los archivos. Asegúrese de que los nombres de archivo para todos los artefactos del proyecto de BizTalk son únicos.  
  
-   Asegúrese de que los nombres de tipo para todos los artefactos del proyecto de BizTalk son únicos.  
  
## <a name="building-any-c-workflow-project-with-biztalk-mapper-shows-a-warning-regarding-version-conflict-for-envdtedll"></a>La generación de un proyecto de flujo de trabajo C# con el Asignador de BizTalk muestra una advertencia relacionada con el conflicto de versiones de EnvDTE.dll  
  
### <a name="problem"></a>Problema  
 La generación de un proyecto de flujo de trabajo C# con una actividad del Asignador de BizTalk muestra la siguiente advertencia relacionada con el conflicto de versiones de EnvDTE.dll  
  
 No hay forma de resolver el conflicto entre "EnvDTE, Version = 8.0.0.0, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a" y "EnvDTE, Version = 7.0.3300.0, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a". Selección arbitraria de "EnvDTE, Version = 8.0.0.0, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a".  Considere la reasignación del archivo app.config del ensamblado "EnvDTE, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" desde la versión "7.0.3300.0" [] a la versión "8.0.0.0" [C:\Archivos de programa (x86)\Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll] para resolver el conflicto y eliminar la advertencia. C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9): advertencia MSB3247: se encontraron conflictos entre diferentes versiones del mismo ensamblado dependiente.  
  
 WorkflowConsoleApplication3-> C:\Usuarios\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe  
  
### <a name="cause"></a>Causa  
 Esto sucede debido al archivo Microsoft.BizTalk.Mapper.OM.dll al que hace referencia la actividad del Asignador.  
  
### <a name="resolution"></a>Solución  
 Pasar por alto la advertencia.  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas de asignaciones](../core/troubleshooting-maps.md)