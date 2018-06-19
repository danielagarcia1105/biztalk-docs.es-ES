---
title: Comprobar un mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, verifying
- verifying, messages
ms.assetid: df2b72bb-4dc1-4fdd-8f63-35fc73a12151
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f2fdc186e93bd182b3021a3ef8fc258cee59923
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961650"
---
# <a name="verifying-a-message"></a>Comprobación de un mensaje
En esta sección se describe cómo comprobar un mensaje que se ha reparado.  
  
### <a name="to-verify-a-message"></a>Para comprobar un mensaje  
  
1.  En Internet Explorer, abra el sitio MRSR en http://localhost/sites/bassite.  
  
2.  En la ventana principal, haga clic en **documentos**.  
  
3.  En la ventana de documentos, en **las bibliotecas de documentos**, haga clic en  **\< *nombre de departamento*\>_Verifier**.  
  
4.  En la ventana de comprobar, haga clic en **Bandeja de entrada**.  
  
5.  En la ventana de la Bandeja de entrada de comprobar, seleccione el título del mensaje, haga clic en la flecha situada a la derecha del título del mensaje y, a continuación, haga clic en **editar en Microsoft Office InfoPath**.  
  
6.  En el **descarga de archivos** cuadro de diálogo, haga clic en **abiertos**.  
  
7.  En los Roles actuales: RekeyVerify panel de la [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana, haga clic en **errores**. Revise cualquier error que se muestra en el **Parse y errores de validación XML** cuadro y **errores de validación de BRE** cuadro.  
  
8.  En el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forman, desplácese a la ubicación del error y compruebe que se ha corregido el error. Puede ver ¿cuál fue el error original, haga clic en **errores** en la función actual: RekeyVerify panel y ver el error en uno de los paneles de error. También puede comparar las versiones sin reparar y reparadas del mensaje, haga clic en **detalles del mensaje** en la función actual: RekeyVerify panel.  
  
9. Para asegurarse de que el mensaje se validará, haga clic en **validación** en la función actual: RekeyVerify panel y, a continuación, haga clic en **mensaje Validate**.  
  
    > [!NOTE]
    >  El panel de resultados de validación del mensaje en la función actual: panel RekeyVerify indica todos los campos en el mensaje que necesita para la regeneración de claves. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]marca estos campos en el panel de mensajes con un asterisco rojo.  
  
10. Regenerar los datos en todos los campos en el panel de mensajes marcados con un asterisco rojo (lo que indica que los datos deben regeneración antes de su envío).  
  
    > [!NOTE]
    >  Puede mostrar los datos que necesita para la regeneración de claves en campos de mensaje, haga clic en **detalles del mensaje** en la función actual: RekeyVerify panel y para desplazarse por el mensaje original para el campo. Esto es así a menos que se produjo un error de validación en uno de los campos de regeneración de claves en el mensaje original, en cuyo caso tendrá que reparar el campo cuando se la regenerar.  
  
11. Haga clic en **validación** en el **rol actual: RekeyVerify** panel y, a continuación, haga clic en **mensaje Validate**. Compruebe que el panel de resultados muestra el mensaje **el mensaje es válido**.  
  
12. Haga clic en **enviar** en el [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana.  
  
    > [!NOTE]
    >  Al hacer clic en **enviar**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] realiza la validación XML en el mensaje. Si la validación no se realiza correctamente, debe corregir los errores de validación antes de continuar.  
  
13. En el cuadro de diálogo Enviar mensaje, haga clic en **Accept** para enviar el mensaje comprobado con cambios aceptados. Haga clic en **rechazar** para enviar el mensaje con los cambios rechazados. Haga clic en **cancelar** cancelar el envío y volver al formulario.  
  
    > [!NOTE]
    >  Si acepta los cambios en el mensaje, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] realiza comprobaciones de BRE en el mensaje.  
  
    > [!NOTE]
    >  Si se rechazan los cambios en el mensaje, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] devuelve el mensaje a la primera fase del flujo de trabajo (crear o reparar) y restablece el flujo de trabajo de reparación.  
  
14. En la página Asistente para firmas digitales para seleccionar el certificado para firmar el formulario, seleccione el certificado que desea utilizar para firmar el formulario (es decir, el certificado que ha creado para el Comprobador) y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Para comprobar la validez de una firma digital, haga clic en **firmas digitales** en el **herramientas** menú, haga clic en la firma digital que se desea comprobar y, a continuación, haga clic en **Ver formulario firmado**. Si necesita agregar otra firma para este rol, puede hacerlo en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] consola de administración.  
  
15. En la página Asistente para firmas digitales para escribir comentarios, haga clic en **finalizar**.  
  
16. En la página Asistente para firmas digitales para comprobar el formulario, compruebe que el mensaje que se va a iniciar sesión es correcto. Haga clic en **Ver certificado** si desea comprobar que se usa la firma correcta. Haga clic en **he comprobado el contenido antes de la firma**y, a continuación, haga clic en **inicio de sesión**.  
  
17. En la ventana de comprobar la firma Digital, haga clic en **cerrar**.  
  
18. En el cuadro de diálogo de éxito de envío, haga clic en **Aceptar**.  
  
19. Cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana.  
  
20. En el sitio MRSR, haga clic en **documentos y listas**. Si hace clic en **Accept** para aceptar los cambios en el paso 13, compruebe que la \<nombre de departamento\>_Approve biblioteca de documentos contiene el mensaje que se ha modificado recientemente. Si ya tenía abrir la ventana de documentos y listas, haga clic en **actualizar** en el **vista** menú. Si hace clic en **rechazar** para rechazar los cambios en el paso 13, compruebe que la  *\<nombre_equipo\>*_Outbox biblioteca de documentos contiene el mensaje que se ha modificado recientemente.