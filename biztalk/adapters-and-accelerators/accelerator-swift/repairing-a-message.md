---
title: Reparación de un mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
ms.assetid: 3a61b73b-5433-4249-b580-6194ccb4aebc
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4489e463257f811fe2c71efea49880940751c66a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="repairing-a-message"></a>Reparación de un mensaje
En esta sección se describe cómo reparar un mensaje que no se pudo validar.  
  
### <a name="to-repair-a-message"></a>Para reparar un mensaje  
  
1.  En Internet Explorer, abra el sitio MRSR en http://localhost/sites/bassite.  
  
2.  En la ventana principal, haga clic en **documentos**.  
  
3.  En la ventana de documentos, en **las bibliotecas de documentos**, haga clic en  **\< *nombre de departamento*\>**_**taller de reparación**.  
  
4.  En el \< *nombre de departamento*\>_Repair ventana, haga clic en **Bandeja de entrada**.  
  
5.  En la ventana de la Bandeja de entrada, seleccione el título del mensaje, haga clic en la flecha situada a la derecha del título del mensaje y, a continuación, haga clic en **editar en Microsoft Office InfoPath**.  
  
6.  En el panel de Acelerador de SWIFT de la [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana 2007, asegúrese de que **errores** está seleccionada. Revise cualquier error que se muestra en el **Parse y errores de validación XML**, **errores de validación de BRE**, y **errores en tiempo de ejecución** cuadros.  
  
7.  En el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario, desplácese hasta la ubicación del error y corrija el error. Si es un error de validación de XML, el error se resaltará en rojo.  
  
    > [!NOTE]
    >  Errores de validación de BRE no aparecerán resaltados en rojo en el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario. Para obtener más información acerca de los errores de validación del BRE, consulte [códigos de Error de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md).  
  
    > [!NOTE]
    >  Si el error se produce en un campo que está acompañado por una lista desplegable, no podrá ver el valor original que produjo el error. El campo mostrará "Select" en lugar del valor original. Seleccione el valor adecuado en la lista desplegable.  
  
8.  Para asegurarse de que el mensaje se validará, haga clic en **validación** en la función actual: reparar panel y, a continuación, haga clic en **mensaje Validate**. Compruebe que el panel de resultados muestra **el mensaje es válido**.  
  
9. En el [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana, haga clic en **enviar**.  
  
    > [!NOTE]
    >  Al hacer clic en **enviar**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] realiza la validación XML en el mensaje. Si la validación no se realiza correctamente, debe corregir los errores de validación antes de continuar.  
  
10. En el cuadro de diálogo Enviar mensaje, haga clic en **Accept** para enviar el mensaje reparado con cambios aceptados, haga clic en **rechazar** rechazar los cambios, o haga clic en **cancelar** Cancelar el envío y se devuelve al formulario.  
  
    > [!NOTE]
    >  Si acepta los cambios en el mensaje, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] realiza comprobaciones de BRE en el mensaje.  
  
    > [!NOTE]
    >  Si lo rechaza los cambios en el mensaje en la fase de reparación, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enruta el mensaje en el cuadro de mensajes y entradas en el Visor de eventos un mensaje de error "no se pudieron restablecer a la primera fase del flujo de trabajo.".  
  
11. Si hace clic en **Accept** o **rechazar** en el paso 10, en el **Asistente para firmas digitales** página, seleccione el certificado que desea utilizar para firmar el formulario (el certificado que creado para el taller de reparación) y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Para comprobar la validez de una firma digital, haga clic en **firmas digitales** en el **herramientas** menú, haga clic en la firma digital que se desea comprobar y, a continuación, haga clic en **Ver formulario firmado**.  
  
12. En la página Asistente para firmas digitales para escribir un comentario, haga clic en **finalizar**.  
  
13. En la página Asistente para firmas digitales para comprobar el formulario, compruebe que el mensaje que se va a iniciar sesión y su firma son correctas. Haga clic en **he comprobado el contenido antes de la firma**y, a continuación, haga clic en **inicio de sesión**.  
  
14. En la ventana de comprobar la firma Digital, haga clic en **cerrar**.  
  
15. En el cuadro de diálogo de éxito de envío, haga clic en **Aceptar**.  
  
16. Cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana.  
  
17. En el sitio MRSR, haga clic en **documentos**. Si hace clic en **Accept** para aceptar los cambios en el paso 11, compruebe que la  *\<nombre de departamento\>*_ReKeyVerify biblioteca de documentos contiene el mensaje que acaba de reparar. Si hace clic en **rechazar** para rechazar los cambios en el paso 11, compruebe que la biblioteca de documentos de A4SWIFT_Outbox contiene el mensaje que se ha modificado recientemente.