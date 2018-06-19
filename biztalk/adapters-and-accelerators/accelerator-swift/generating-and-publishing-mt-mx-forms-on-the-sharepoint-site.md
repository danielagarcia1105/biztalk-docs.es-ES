---
title: Generar y publicar formularios de MT MX en el sitio de SharePoint | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4adf7117-11ad-4a8e-8d6a-fd78c5e496a3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c8bd8248a916d1e98571551a8561119b6377329
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
ms.locfileid: "25965354"
---
# <a name="generating-and-publishing-mtmx-forms-on-the-sharepoint-site"></a>Generar y publicar formularios de MT/MX en el sitio de SharePoint
**Para generar y publicar MT/MX formularios en un sitio de SharePoint:**  
  
1.  Descargar la utilidad de generador del formulario y lo guarda localmente en el equipo.  
  
2.  Abra la **FormGenerator.sln** desde la carpeta descargó anteriormente y compile la solución.  
  
3.  En un símbolo del sistema, tener acceso a la carpeta del archivo ejecutable compilado (FormGenerator.exe). Por ejemplo, si ha creado la utilidad en modo de depuración, tener acceso a la **... \bin\Debug** carpeta.  
  
4.  Escriba FormGenerator.exe [-b] [-\<no. de las rutas de acceso de carpeta de plantilla\>]  
  
     `<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`. Reemplace los parámetros con los nombres de carpeta recién creada.  
  
5.  El comando anterior también generará el esquema de sobres necesario para la reparación de mensajes de MX.  
  
6.  Vaya a la carpeta de salida \<DestinationFolderPath\>. En \<DestinationFolderPath\>, abra la carpeta de la plantilla de formulario de InfoPath para los que desea generar el formulario. Por ejemplo, si desea generar el formulario de InfoPath MT103, a continuación, abra la carpeta MT103 en la DestinationFolderPath y abra el TemplateDS.sln.  
  
7.  En el Explorador de soluciones, haga doble clic en el **manifest.xsf**. Se abrirá el archivo de diseño del formulario de InfoPath que tardará algún tiempo en obtener abierto.  
  
    > [!NOTE]
    >  El archivo manifest.xsf mensajes de MX puede tardar 2 y 5 minutos en obtener abierto.  
  
8.  En el archivo manifest.xsf, vaya a **Herramientas -> Opciones de formato - > seguridad y confianza** opción de menú. Compruebe el **plena confianza** opción debe estar habilitada para el permiso.  
  
9. Seleccione el **firmar esta plantilla de formulario** casilla de verificación. Haga clic en **Seleccionar certificado**. En este caso, seleccione el certificado con el que va a firmar el formulario. Haga clic en **Aceptar**.  
  
10. Guardar **manifest.xsf**.  
  
11. Vaya a **Ver -> tareas de diseño**. En el panel de tareas de diseño, haga clic en **publicar la plantilla de formulario** opción.  
  
12. En la ventana del Asistente para publicación, seleccione **a una ubicación de red** y haga clic en **siguiente**.  
  
13. En el formulario plantilla ruta de acceso y cuadro de texto Nombre, escriba  **http://localhost/sites/BASSite/Templates/ \<MessageType\>.xsn** y tipo **\<MessageType\>** en el formulario Cuadro de texto de nombre de plantilla y haga clic en **siguiente**.  
  
14. Haga clic en **Siguiente**.  
  
15. Haga clic en **publicar y cerrar**.  
  
16. En Internet Explorer, abra el sitio de SharePoint **http://localhost/sites/bassite/templates**.  
  
17. Seleccione  **\<MessageType\>**, haga clic en la flecha abajo situada junto a él y, a continuación, haga clic en **editar propiedades**.  
  
18. En las plantillas:\< MessageType\> ventana, en el cuadro Namespace:  
  
    -   Si va a generar los formularios de InfoPath de MT, escriba: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**  
  
    -   Si va a generar los formularios de InfoPath MX, escriba:  **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_ \<MessageName\>**  
  
         Esto le ayudará a identificar la instancia de mensaje con la plantilla correspondiente.  
  
19. Haga clic en **guardar y cerrar**.