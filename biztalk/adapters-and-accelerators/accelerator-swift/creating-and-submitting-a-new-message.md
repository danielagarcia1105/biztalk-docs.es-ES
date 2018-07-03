---
title: Crear y enviar un mensaje nuevo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, messages
- submitting, messages
- messages, submitting
- messages, creating
ms.assetid: 88b7a2d3-44a4-44e4-ba8c-527c10290925
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbaef31e6bf47538e57b4c509efcb7a8cf565162
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970101"
---
# <a name="creating-and-submitting-a-new-message"></a>Crear y enviar un mensaje nuevo
En esta sección se describe cómo enviar un mensaje nuevo. Como con el mensaje reparado, un nuevo mensaje necesario comprobar y aprobado por personas que no sea el creador del mensaje.  

 Para enviar un mensaje nuevo, debe cargar en la biblioteca de documentos nuevos mensajes de SWIFT un archivo de plantilla de mensaje para el tipo de mensaje que desea enviar. Puede cargar una plantilla de mensaje único manualmente, o puede cargar todas las plantillas de mensaje mediante la herramienta FormPublish.  

### <a name="to-upload-a-single-message-template-into-the-new-document-library"></a>Para cargar una plantilla de mensaje único en la nueva biblioteca de documentos  

1.  Consulte la sección [formulario Generador de utilidad para generar formularios de InfoPath de MT/MX](../../adapters-and-accelerators/accelerator-swift/form-generator-utility-to-generate-mt-mx-infopath-forms.md) para obtener instrucciones.  

### <a name="to-create-and-submit-a-new-message"></a>Para crear y enviar un mensaje nuevo  

1. En Internet Explorer, abra el sitio MRSR en http://localhost/sites/bassite.  

2. Haga clic en **documentos**y, a continuación, haga clic en **nuevos mensajes de SWIFT**.  

3. En la página nuevos mensajes de SWIFT, haga doble clic en el nombre de la categoría que contiene el tipo del mensaje que le gustaría crear.  

4. Haga clic en la plantilla de formulario para el mensaje que se va a crear.  

5. En el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana, en el mensaje de formulario, tipo de datos de mensaje para todos los campos obligatorios (como conocido por un asterisco) y los campos opcionales que desea usar.  

6. Para buscar un BIC, en la función actual: crear el panel, haga clic en **búsqueda BIC**.  

7. Escriba el nombre de la institución financiera, el código del banco y el país o región y, a continuación, haga clic en **búsqueda**.  

8. En el panel de búsqueda BIC, copie el BIC en el campo de código de banco adecuado con el formato de mensaje.  

9. En el rol actual: crear el panel, haga clic en **validación**y, a continuación, haga clic en **validar mensajes**.  

10. En el panel de resultados de la función actual: crear el panel, determinar los errores que deba solucionar en el mensaje.  

    > [!NOTE]
    >  Solo puede enviar un nuevo mensaje si se han corregido todos los errores de validación en el mensaje.  

11. En la barra de herramientas estándar en la parte superior de la ventana, haga clic en **enviar**.  

12. En la página del Asistente para firmas digitales para seleccionar el certificado para firmar el formulario, seleccione el certificado que se va a usar para firmar el formulario (es decir, el certificado que ha creado para el creador). Haga clic en **Ver certificado** si desea comprobar que está usando la firma correcta. Haga clic en **Siguiente**.  

    > [!NOTE]
    >  Para comprobar la validez de una firma digital, haga clic en **firmas digitales** en el **herramientas** menú, haga clic en la firma digital que desee comprobar y, a continuación, haga clic en **Ver formulario firmado**.  

13. En la página del Asistente para firmas digitales para escribir comentarios, haga clic en **finalizar**.  

14. En la página del Asistente para firmas digitales para comprobar el formulario, compruebe que el mensaje que se va a iniciar sesión es correcto. Haga clic en **Ver certificado** si desea comprobar que está usando la firma correcta. Haga clic en **he comprobado el contenido antes de iniciar sesión**y, a continuación, haga clic en **sesión**.  

15. En la ventana de comprobar la firma Digital, haga clic en **cerrar**.  

16. En el cuadro de diálogo de éxito de envío, haga clic en **Aceptar**.  

17. Cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana.
