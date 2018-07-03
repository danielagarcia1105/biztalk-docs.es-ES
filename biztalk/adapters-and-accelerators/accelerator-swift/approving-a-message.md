---
title: Aprobación de un mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, approving
- approving messages
ms.assetid: e6abfef3-aab2-470e-a7a7-a6d091ffba53
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c565f40c6c455456101521414edf0c377411014
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967109"
---
# <a name="approving-a-message"></a>Aprobación de un mensaje
En esta sección se describe cómo aprobar un mensaje que se ha reparado y comprobado.  

### <a name="to-approve-a-message"></a>Para aprobar un mensaje  

1. En Internet Explorer, abra el sitio MRSR en http://localhost/sites/bassite.  

2. En la ventana principal, haga clic en **documentos**.  

3. En la ventana de documentos en **las bibliotecas de documentos**, haga clic en  **\< *nombre de departamento*\>_Approver**.  

4. En el \<nombre de departamento\>_Approver ventana, haga clic en **Bandeja de entrada**.  

5. En la ventana de la Bandeja de entrada, seleccione el título del mensaje, haga clic en la flecha situada a la derecha del título del mensaje y, a continuación, haga clic en **editar en Microsoft Office InfoPath**.  

6. En el panel del Acelerador de SWIFT del [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana, haga clic en **errores**. Revise cualquier error que se muestra en el **Parse y errores de validación XML** cuadro, el **BRE los errores de validación** cuadro y el **errores en tiempo de ejecución** cuadro.  

7. En el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forman, desplácese a la ubicación del error y compruebe que se ha corregido el error. Puede ver qué error original haciendo **errores** en el rol actual: aprobar panel y ver el error en uno de los paneles de error. También puede comparar las versiones sin reparar y reparadas del mensaje, haga clic en **detalles del mensaje** en el rol actual: aprobar el panel.  

8. Para asegurarse de que se validará el mensaje, haga clic en **validación** en el rol actual: aprobar el panel y, a continuación, haga clic en **validar mensajes**. Compruebe que el panel de resultados muestra el mensaje **el mensaje es válido**.  

9. Si aprueba los cambios que se realizaron en el documento, en el [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana, haga clic en **enviar**.  

   > [!NOTE]
   >  Al hacer clic en **enviar**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] realiza la validación de XML en el mensaje. Si la validación no se realiza correctamente, debe corregir los errores de validación antes de continuar.  

10. En el cuadro de diálogo Enviar mensaje, haga clic en **Accept** para enviar el mensaje aprobado con cambios aceptados. Haga clic en **rechazar** para enviar el mensaje con los cambios que se rechazó. Haga clic en **cancelar** para cancelar el envío y volver al formulario.  

    > [!NOTE]
    >  Si acepta el mensaje cambia [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] realiza validaciones del BRE en el mensaje.  
    > 
    > [!NOTE]
    >  Si lo rechaza el mensaje cambia [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] devuelve el mensaje a la primera fase del flujo de trabajo (crear o reparar) y restablece el flujo de trabajo de reparación.  

11. En la página del Asistente para firmas digitales para seleccionar el certificado para firmar el formulario, seleccione el certificado que se va a usar para firmar el formulario (es decir, el certificado que ha creado para el aprobador). Haga clic en **Ver certificado** si desea comprobar que está usando la firma correcta. Haga clic en **Siguiente**.  

    > [!NOTE]
    >  Para comprobar la validez de una firma digital, haga clic en **firmas digitales** en el **herramientas** menú, haga clic en la firma digital que desee comprobar y, a continuación, haga clic en **Ver formulario firmado**. También puede ver qué roles han registrado previamente el formulario (solo se puede firmar un formulario por una persona una vez por cada flujo de trabajo), haga clic en **firmas digitales** en el **herramientas** menú. Si necesita agregar otra firma de este rol, puede hacerlo en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] consola de administración.  

12. En la página del Asistente para firmas digitales para escribir comentarios, haga clic en **finalizar**.  

13. En la página del Asistente para firmas digitales para comprobar el formulario, compruebe que el mensaje que se va a iniciar sesión es correcto. Haga clic en **Ver certificado** si desea comprobar que está usando la firma correcta. Haga clic en **he comprobado el contenido antes de iniciar sesión**y, a continuación, haga clic en **sesión**.  

14. En la ventana de comprobar la firma Digital, haga clic en **cerrar**.  

15. En el cuadro de diálogo de éxito de envío, haga clic en **Aceptar**.  

16. Cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana.  

17. En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, abra la carpeta que configuró para recibir los mensajes enviados. Compruebe que la carpeta contiene el mensaje aprobado. Abra el mensaje en un editor de texto para comprobar que se ha corregido el mensaje.
