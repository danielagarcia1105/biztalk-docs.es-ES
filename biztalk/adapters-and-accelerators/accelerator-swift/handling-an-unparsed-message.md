---
title: Controla un mensaje sin analizar | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unparsed messages
- messages, unparsed messages
ms.assetid: c6a67ff3-3295-489f-9d5f-fb35b2bf8b19
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b24b7db4013e5e1f8fdb03c1278a19dc070d0e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998669"
---
# <a name="handling-an-unparsed-message"></a>Controla un mensaje sin analizar
En esta sección se describe cómo controlar un mensaje sin analizar. A diferencia de los mensajes que no superan la validación, no se puede reparar un mensaje que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no se puede analizar. Reparación de mensajes y nuevo envío muestra el mensaje y la naturaleza del error de análisis y le permite imprimir el mensaje o guardarlo en un archivo local. A continuación, puede notificar a la entidad que envió el mensaje a la naturaleza del error de análisis específica.  

### <a name="to-handle-an-unparsed-message"></a>Para controlar un mensaje sin analizar  

1. En Internet Explorer, abra el sitio MRSR en http://localhost/sites/bassite.  

2. En la ventana principal, haga clic en **documentos**.  

3. En la ventana de documentos en **las bibliotecas de documentos**, haga clic en **Unparsed**.  

4. En la ventana sin analizar, haga clic en **Bandeja de entrada**.  

5. En la ventana de la Bandeja de entrada sin analizar, seleccione el mensaje que no se ha sido analizar, haga clic en la flecha situada a la derecha del mensaje y, a continuación, haga clic en **editar en Microsoft Office InfoPath**.  

6. En el panel del Acelerador de SWIFT, haga clic en **errores**.  

7. En el panel de análisis y errores de validación XML, lea el error de análisis.  

8. En el panel de mensajes sin analizar, revise el mensaje.  

   > [!NOTE]
   >  Si desea imprimir el mensaje, en el panel de mensajes sin analizar, en el **archivo** menú, haga clic en **imprimir**.  
   > 
   > [!NOTE]
   >  Si desea guardar el mensaje en un archivo local, en el panel de mensajes sin analizar, en el **archivo** menú, haga clic en **Guardar como**. En el **Guardar como** cuadro de diálogo el **guardar en** lista desplegable, desplácese a la carpeta que desea guardar el archivo y, a continuación, haga clic en **Aceptar**. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] guarda el mensaje en formato XML.  

9. En el panel de mensajes sin analizar, realice los cambios necesarios y, a continuación, haga clic en **enviar**.  

    > [!NOTE]
    >  No se puede validar un mensaje sin analizar que se ha reparado.  

10. En el cuadro de diálogo Enviar mensaje, haga clic en **Accept** para enviar el mensaje reparado con cambios aceptados, haga clic en **rechazar** rechazar los cambios, o haga clic en **cancelar** Cancelar el envío y volver al formulario.  

11. Si hizo clic en **Accept** o **rechazar** en el paso 11, en la página del Asistente para la firma Digital, seleccione el certificado que desea utilizar para firmar el formulario (el certificado que ha creado para el taller de reparación) y, a continuación, Haga clic en **siguiente**.  

    > [!NOTE]
    >  Para comprobar la validez de una firma digital, haga clic en **firmas digitales** en el **herramientas** menú, haga clic en la firma digital que desee comprobar y, a continuación, haga clic en **Ver formulario firmado**.  

    > [!NOTE]
    >  Cualquier usuario que realiza cualquier rol puede enviar un mensaje sin analizar que ha reparado.  

12. En la página del Asistente para firmas digitales para escribir comentarios, haga clic en **finalizar**.  

13. En la página del Asistente para firmas digitales para comprobar el formulario, compruebe que el mensaje que se va a iniciar sesión es correcto. Haga clic en **Ver certificado** si desea comprobar que está usando la firma correcta. Haga clic en **he comprobado el contenido antes de iniciar sesión**y, a continuación, haga clic en **sesión**.  

14. En la ventana de comprobar la firma Digital, haga clic en **cerrar**.  

15. En el cuadro de diálogo de éxito de envío, haga clic en **Aceptar**.  

16. Cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana.
