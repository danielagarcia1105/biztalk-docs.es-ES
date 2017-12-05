---
title: "Error en la lista de tareas de compilación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building, errors
- errors, building
ms.assetid: 05b36511-3031-4e13-ac2f-bfdbec0f48cb
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aeef8ac3defc17f4c9bf0fbddedf6d389a1263e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="build-errors-in-the-task-list"></a>Error en la lista de tareas de compilación
Al generar un proyecto o una solución, los resultados aparecen en la ventana Resultados, y los errores y las advertencias, en la lista de tareas.  
  
 Los errores y las advertencias se muestran en la lista de tareas. Puede hacer doble clic en el error para que se aplique el foco al objeto que no esté configurado correctamente.   
  
> [!NOTE]
>  Durante el proceso de generación, el compilador no valida los XPath. Recuerde usar una sintaxis válida de XPath.  
  
## <a name="insufficient-configuration-action"></a>Acción de configuración incompleta  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!CAUTION]
>  Aunque el Diseñador de orquestaciones proporciona advertencias de configuración incompleta en los casos que puede, la falta de tales advertencias no garantiza la compilación correcta de la orquestación.  
  
## <a name="compiler-asks-if-you-are-missing-an-assembly-reference"></a>El compilador pregunta si falta una referencia de ensamblado  
  
### <a name="problem"></a>Problema  
 Al compilar la orquestación recibe un mensaje de error que termina con la pregunta "¿falta una referencia de ensamblado?" Dos de los mensajes más comunes son:  
  
-   El tipo o el nombre del espacio de nombres 'X' no existe en el espacio de nombres 'Y' (¿falta una referencia de ensamblado?)  
  
-   El identificador 'X' no existe en 'Y'; (¿falta una referencia de ensamblado?)  
  
### <a name="cause"></a>Causa  
 La causa de este error puede ser cualquiera de las siguientes.  
  
-   El proyecto no hace referencia a uno o varios ensamblados necesarios.  
  
-   El proyecto tiene una asignación u otro tipo de objeto que tiene el mismo nombre que el proyecto.  
  
-   El proyecto usa esquemas de Proceso de Interfaz de Socio (PIP) basados en el lenguaje de definición de esquemas XML (XSD) y contiene esquemas XSD en una subcarpeta cuyo nombre es System.  
  
-   El proyecto usa una propiedad global cuyo espacio de nombres es un subconjunto del espacio de nombres actual del proyecto. Un ejemplo de ello es el uso del espacio de nombres "File.ReceivedFileName" de propiedad global en una orquestación contenida en el proyecto "Accounts.FILE".  
  
### <a name="resolution"></a>Solución  
 Según la causa del problema, la solución podría ser cualquiera de las siguientes:  
  
-   Agregar una referencia a los ensamblados que faltan que el proyecto necesita.  
  
-   Cambiar el nombre de la asignación o del objeto de otro tipo por otro distinto del nombre del proyecto. Normalmente, puede hacerlo usando la página de propiedades del objeto (por ejemplo, la página de propiedades de asignación contiene una propiedad Nombre).  
  
-   Cambiar el espacio de nombres correspondiente a los esquemas en Visual Studio. Para hacer esto con Visual Studio, haga clic en **mostrar todos los archivos** en el **proyecto** menú y, a continuación, expanda el **System** nodo en el Explorador de soluciones. Haga clic en cada archivo en la carpeta del sistema y en todas las subcarpetas y, a continuación, cambie la entrada de espacio de nombres en la ventana Propiedades de forma que cualquier aparición de **System** se conviertan en _**System**. Por ejemplo, cambiar el **MyProject.System.SubFolder** espacio de nombres **el MyProject._System.Subfolder** espacio de nombres. Para obtener más información acerca de este problema, consulte el artículo de KB [916649](http://support.microsoft.com/?kbid=916649).  
  
-   Quite del proyecto el espacio de nombres de la propiedad global objeto de conflicto.  
  
## <a name="you-receive-a-message-has-not-been-initialized-in-construct-statement-error-when-building-your-project"></a>Se recibe el error "no se ha inicializado mensaje en la instrucción de construcción" al generar el proyecto  
  
### <a name="problem"></a>Problema  
 Al compilar la aplicación de BizTalk, recibe el error "no se ha inicializado mensaje en la instrucción de construcción".  
  
### <a name="cause"></a>Causa  
 Al construir un mensaje, se especifican todas las variables de éste. A continuación, se realizan asignaciones al mensaje o las partes que lo componen. Si parte de una asignación de mensajes específico se incluye en otro **construir mensaje** forma, puede recibir el mensaje de error de inicialización.  
  
### <a name="resolution"></a>Solución  
 Para resolver este comportamiento, asegúrese de que incluye todas las partes de una asignación de mensaje específica en la misma **construir mensaje** forma. Un problema de soporte relacionada, consulte el artículo de KB [870606](http://support.microsoft.com/?kbid=870606).  
  
 También puede resolver este comportamiento creando el mensaje en una **construir** forma antes de utilizar una instancia del mismo en un **expresión** forma. Por ejemplo, el código siguiente producirá un error si se coloca en un **expresión** forma:  
  
```  
XMLDOM = new System.Xml.XmlDocument();  
POAckMsg = XMLDOM;  
```  
  
 Para solucionar el problema, cree la instancia de XMLDOM en una **construir** forma y, a continuación, realice la asignación en un nivel inferior **expresión** forma.  
  
## <a name="you-receive-a-use-of-unconstructed-message-error-when-building-your-project"></a>Se recibe el error "utilización de mensaje no construido" al generar el proyecto  
  
### <a name="problem"></a>Problema  
 Cuando se compila el proyecto de BizTalk, recibe el error "el uso de mensaje no construido '\<mensaje\>'".  
  
### <a name="cause"></a>Causa  
 Este error se produce cuando se usa un mensaje no construido un **enviar** forma.  
  
### <a name="resolution"></a>Solución  
 Para resolver este problema, agregue un **construir mensaje** forma a la orquestación. Incluir el **construir mensaje** forma antes de la **enviar** forma a la que está enlazado al servicio Web.  
  
 Para obtener más información sobre este error y los servicios Web, consulte el artículo de KB [921043](http://support.microsoft.com/?kbid=921043).  
  
## <a name="setting-a-transaction-level-for-a-scope-results-in-an-error"></a>Al establecer un nivel de transacción para un ámbito se produce un error  
  
### <a name="problem"></a>Problema  
 Después de configurar el tipo de transacción para un ámbito u otra entidad que admite transacciones en una orquestación, se recibe el error "Una orquestación no transaccional no puede contener ninguna otra transacción".  
  
### <a name="cause"></a>Causa  
 Este error se produce cuando se intenta establecer el tipo de transacción de un ámbito (u otra entidad) de una orquestación en "Atómica" o "Larga ejecución" pero el tipo de transacción de la propia orquestación es "Ninguna".  
  
### <a name="resolution"></a>Solución  
 Asegurarse de que la configuración de tipos de transacción de la orquestación y de los objetos que la componen sean compatibles.  
  
## <a name="project-build-results-in-the-error-you-must-specify-at-least-one-already-initialized-correlation-set-for-a-non-activation-receive-that-is-on-a-non-selfcorrelating-port"></a>Al generar el proyecto se produce el error "debe especificar al menos una correlación ya inicializada establecida para una recepción de no activación de un puerto no autocorrelacionado"  
  
### <a name="problem"></a>Problema  
 Al compilar el proyecto de BizTalk, se recibe el error "debe especificar al menos una correlación ya inicializada establecida para una recepción de no activación de un puerto no autocorrelacionado".  
  
### <a name="cause"></a>Causa  
 Este error puede producirse si la orquestación no tiene activar **recepción** formas (activar = true) o no tiene ningún activar **recepción** formas y no se llama directamente por otra orquestación.  
  
### <a name="resolution"></a>Solución  
 Si no se llama a la orquestación otra orquestación, debe configurar uno de los **recepción** formas se recepciones de activación. Para obtener más información acerca de cómo configurar el **recepción** forma, incluidos los vínculos a correlaciones, vea [cómo configurar la forma recepción](../core/how-to-configure-the-receive-shape.md).  
  
## <a name="you-receive-the-error-assembly-generation-failed----referenced-assembly-assembly-does-not-have-a-strong-name-when-building-your-solution"></a>Recibe el error "Error al generar el ensamblado--hace referencia el ensamblado '\<ensamblado\>' no tiene un nombre seguro" al compilar la solución  
  
### <a name="problem"></a>Problema  
 Recibe el error "Error al generar el ensamblado--hace referencia el ensamblado '\<ensamblado\>' no tiene un nombre seguro" al generar una solución que tiene una orquestación.  
  
### <a name="cause"></a>Causa  
 Este problema se produce cuando se usa un tipo de un ensamblado sin firmar al que se hace referencia en una orquestación.  
  
### <a name="resolution"></a>Solución  
 Aplicar un nombre seguro al ensamblado al que se hace referencia. Si se trata de un ensamblado personalizado que es posible volver a compilar, use la herramienta de nombre seguro para crear un archivo .snk (de clave) y, a continuación, haga referencia a este archivo de clave en las propiedades de ensamblado del proyecto. Para obtener más información sobre nombres seguros de un ensamblado, vea [cómo configurar un archivo de clave de ensamblado de nombre seguro](../core/how-to-configure-a-strong-name-assembly-key-file.md).  
  
## <a name="the-error-failed-to-add-resources-change-requests-failed-for-some-resources-occurs-when-deploying-an-orchestration"></a>El error "No se pudieron agregar los recursos. Error en las solicitudes de cambio de algunos recursos" se produce al implementar una orquestación  
  
### <a name="problem"></a>Problema  
 Al implementar una orquestación, aparece un error parecido al siguiente y no se puede continuar con la implementación de la orquestación:  
  
```  
Failed to add resource(s). Change requests failed for some resources. BizTalkAssemblyResourceManager failed to complete end type change request. Object reference not set to an instance of an object.  
```  
  
### <a name="cause"></a>Causa  
 Este error puede producirse si la orquestación contiene cualquier objeto que use palabras clave de C#.  
  
### <a name="resolution"></a>Solución  
 Quitar todas las palabras clave de C# de la orquestación. Para obtener una lista de palabras clave de C#, vea [http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346).  
  
## <a name="you-receive-an-invalid-property-value-error-when-compiling-your-orchestration"></a>Se recibe un error "Valor de propiedad no válido" al compilar la orquestación  
  
### <a name="problem"></a>Problema  
 Se recibe el cuadro de diálogo de error "Valor de propiedad no válido" al generar la orquestación.  
  
### <a name="cause"></a>Causa  
 Uno o varios de los objetos de la solución tiene el mismo nombre que otro objeto. Por ejemplo, un nombre de mensaje es igual que un nombre de puerto.  
  
### <a name="resolution"></a>Solución  
 Asegurarse de que todos los objetos de la solución tengan un nombre único. Puede minimizar el riesgo de que se produzca este error respetando una convención de nomenclatura.  
  
## <a name="see-also"></a>Vea también  
 [Cómo generar orquestaciones](../core/how-to-build-orchestrations.md)