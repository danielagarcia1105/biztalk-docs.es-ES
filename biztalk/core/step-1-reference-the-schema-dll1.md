---
title: 'Paso 1: Hacer referencia a la DLL1 esquema | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47e4b773-e484-4931-9ab2-b8dd0080ea1c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c2d5051c7dfd3c0f971b34922ca4e5747117c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-reference-the-schema-dll"></a>Paso 1: Hacer referencia al esquema DLL
En BizTalk, los mensajes son inmutables. Por tanto, para cambiar un valor de propiedad, debe crear y modificar un nuevo mensaje. Puede crear y modificar el nuevo mensaje mediante la inserción de una forma de asignación del mensaje entre las formas de envío y recepción.  
  
 No obstante, debe hacer referencia, en primer lugar, al esquema DLL para obtener acceso a las propiedades de contexto de J.D. Propiedades de contexto de Edwards EnterpriseOne.  
  
### <a name="to-reference-the-schema-dll"></a>Para hacer referencia al esquema DLL  
  
1.  Cree una carpeta de trabajo, por ejemplo, c:\class\JDE\BeginDoc, para su proyecto, y una carpeta en la que pondrá el XML de prueba, por ejemplo, c:\class\JDE\input.  
  
2.  Crear un puerto de envío de petición-respuesta estático para enviar la solicitud a J.D. Edwards EnterpriseOne.  
  
     ![Propiedades de transporte de JDOneWorld](../core/media/example-2waysendport-ow.gif "example_2waysendport_OW")  
  
3.  En el editor de soluciones, haga clic con el botón secundario en su proyecto.  
  
    1.  Seleccione **agregar**, seleccione **agregar elementos generados**y, a continuación, haga clic en **agregar adaptador**.  
  
    2.  Seleccione el adaptador de Microsoft BizTalk para J.D. Edwards EnterpriseOne y el puerto que acaba de crear.  
  
    3.  En el **Asistente para agregar adaptador**, seleccione **CSALES\B4200310**.  
  
    4.  Haga clic en **finalizar** para generar el esquema que contiene el formato del mensaje.  
  
     ![Asistente para agregar adaptador](../core/media/add-adapter-wizard.gif "add_adapter_wizard")  
  
4.  En Visual Studio, abra el Explorador de soluciones.  
  
5.  Haga clic en **referencias**y, a continuación, seleccione **Agregar referencia**.  
  
6.  En el **Agregar referencia** pantalla, haga clic en el **examinar** botón.  
  
7.  En el **Seleccionar componente** pantalla, vaya a %SystemDrive%\Program programa\Archivos comunes\Microsoft BizTalk Adapters for Enterprise Applications\bin.  
  
8.  Seleccione **Microsoft.Adapters.JDEProperties.dll**y, a continuación, haga clic en **abiertos**.  
  
9. En el **Agregar referencia** pantalla, el archivo DLL aparece en la **componentes seleccionados** sección.  
  
     ![Pantalla de selección de propiedades](../core/media/properties-selection.gif "properties_selection")  
  
10. Haga clic en **Aceptar**.  
  
11. Haga doble clic en la orquestación para obtener acceso al Diseñador de orquestaciones.  
  
     \- O BIEN  
  
     Seleccione **vista**, seleccione **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
     Aparecerá la Vista orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Crear la orquestación](../core/step-2-create-the-orchestration2.md)   
 [Tarea 4: Configurar la forma construir mensaje](../core/task-4-configure-the-construct-message-shape1.md)   
 [Tarea 5: Configurar la forma transformación](../core/task-5-configure-the-transform-shape2.md)   
 [Paso 3: Completar y ejecutar el proyecto](../core/step-3-complete-and-run-the-project1.md)   
 [Paso 4: Crear un XML de ejemplo de BeginDoc](../core/step-4-create-a-sample-xml-begindoc2.md)