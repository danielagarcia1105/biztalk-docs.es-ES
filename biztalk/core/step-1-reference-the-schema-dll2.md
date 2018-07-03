---
title: 'Paso 1: Hacer referencia el esquema DLL2 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1db92227-6164-42b9-b60c-12dd2cae46e2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c58156c64ae9954115ff214518879c4cd17e7417
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984333"
---
# <a name="step-1-reference-the-schema-dll"></a>Paso 1: Hacer referencia al esquema DLL
En BizTalk, los mensajes son inmutables. Por tanto, para cambiar un valor de propiedad, debe crear y modificar un nuevo mensaje. Puede crear y modificar el nuevo mensaje mediante la inserción de una forma de asignación del mensaje entre las formas de envío y recepción.  
  
 No obstante, debe hacer referencia, en primer lugar, al esquema DLL para obtener acceso a las propiedades de contexto de J.D. Propiedades de contexto de Edwards.  
  
### <a name="to-reference-the-schema-dll"></a>Para hacer referencia al esquema DLL  
  
1. Cree una carpeta de trabajo, por ejemplo, c:\class\JDE\BeginDoc, para su proyecto, y una carpeta en la que pondrá el XML de prueba, por ejemplo, c:\class\JDE\input.  
  
2. Crear un puerto de envío de petición-respuesta estático para enviar la solicitud a J.D. Edwards OneWorld.  
  
    ![](../core/media/jde-example-2waysendport-ow.gif "JDE_example_2waysendport_OW")  
  
3. En el editor de soluciones, haga clic con el botón secundario en su proyecto.  
  
   1. Seleccione **agregar**, seleccione **agregar elementos generados**y, a continuación, haga clic en **agregar adaptador**.  
  
   2. Seleccione el adaptador de Microsoft BizTalk para J.D. Edwards OneWorld y el puerto que acaba de crear.  
  
   3. En el **Asistente para agregar adaptador**, seleccione **CSALES\B4200310**.  
  
   4. Haga clic en **finalizar** para generar el esquema que contiene el formato del mensaje.  
  
      ![](../core/media/jde-add-adapter-wizard.gif "JDE_add_adapter_wizard")  
  
4. En Visual Studio, abra el Explorador de soluciones.  
  
5. Haga clic en **referencias**y, a continuación, seleccione **Agregar referencia**.  
  
6. En el **Agregar referencia** pantalla, haga clic en el **examinar** botón.  
  
    ![](../core/media/jde-add-reference-dll.gif "JDE_add_reference_dll")  
  
7. En el **Seleccionar componente** pantalla, vaya a %SystemDrive%\Program programa\Archivos comunes\Microsoft BizTalk Adapters for Enterprise Applications\bin.  
  
8. Seleccione **Microsoft.Adapters.JDEProperties.dll**y, a continuación, haga clic en **abierto**.  
  
9. En el **Agregar referencia** pantalla, el archivo DLL aparece en la **componentes seleccionados** sección.  
  
     ![](../core/media/jde-properties-selection.gif "JDE_properties_selection")  
  
10. Haga clic en **Aceptar**.  
  
11. Haga doble clic en la orquestación para obtener acceso al Diseñador de orquestaciones.  
  
     \- O BIEN  
  
     Seleccione **vista**, seleccione **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  
  
     Aparecerá la Vista orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Crear la orquestación](../core/step-2-create-the-orchestration1.md)   
 [Paso 3: Completar y ejecutar el proyecto](../core/step-3-complete-and-run-the-project2.md)   
 [Paso 4: Crear un BeginDoc de XML de ejemplo](../core/step-4-create-a-sample-xml-begindoc1.md)