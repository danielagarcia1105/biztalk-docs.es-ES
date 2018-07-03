---
title: Generación y publicación de formularios MT-MX en el sitio de SharePoint | Microsoft Docs
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
ms.openlocfilehash: 492eda3b4bf3d3950c084bc9234b52b911b84a2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980053"
---
# <a name="generating-and-publishing-mtmx-forms-on-the-sharepoint-site"></a>Generación y publicación de formularios MT/MX en el sitio de SharePoint
**Para generar y publicar formularios MT/MX en un sitio de SharePoint:**  

1. Descargar la utilidad de generador del formulario y guárdelo localmente en el equipo.  

2. Abra el **FormGenerator.sln** desde la carpeta que descargó anteriormente y compile la solución.  

3. En un símbolo del sistema, vaya a la carpeta del archivo ejecutable compilado (FormGenerator.exe). Por ejemplo, si ha creado la utilidad en modo de depuración, tener acceso a la **... \bin\Debug** carpeta.  

4. Escriba FormGenerator.exe [-b] [-\<no. de las rutas de acceso de carpeta de plantilla\>]  

    `<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`. Reemplace los parámetros con los nombres de carpeta recién creada.  

5. El comando anterior también generará el esquema de sobres necesario para la reparación de mensajes MX.  

6. Vaya a la carpeta de salida \<DestinationFolderPath\>. En \<DestinationFolderPath\>, abra la carpeta de la plantilla de formulario de InfoPath para el que desea generar el formulario. Por ejemplo, si desea generar el formulario de InfoPath MT103, a continuación, abra la carpeta MT103 en el DestinationFolderPath y abra el TemplateDS.sln.  

7. En el Explorador de soluciones, haga doble clic en el **manifest.xsf**. Se abrirá el archivo de diseño del formulario de InfoPath que tardará algún tiempo en obtener abierto.  

   > [!NOTE]
   >  El archivo manifest.xsf de mensajes de MX puede tardar 2 y 5 minutos en obtener abierto.  

8. En el archivo manifest.xsf, vaya a **Herramientas -> Opciones de formato - > seguridad y confianza** opción de menú. Compruebe el **plena confianza** opción debe estar habilitada para el permiso.  

9. Seleccione el **firmar esta plantilla de formulario** casilla de verificación. Haga clic en **Seleccionar certificado**. En este caso, seleccione el certificado con el que desea firmar el formulario. Haga clic en **Aceptar**.  

10. Guardar **manifest.xsf**.  

11. Vaya a **Ver -> tareas de diseño**. En el panel de tareas de diseño, haga clic en **publicar la plantilla de formulario** opción.  

12. En la ventana del Asistente para publicación, seleccione **a una ubicación de red** y haga clic en **siguiente**.  

13. En el formulario plantilla ruta de acceso y cuadro de texto Nombre, escriba <strong>http://localhost/sites/BASSite/Templates/\<MessageType\>.xsn</strong> y tipo **\<MessageType\>** en la plantilla de formulario de cuadro de texto Nombre y haga clic en **siguiente** .  

14. Haga clic en **Siguiente**.  

15. Haga clic en **publicar y cerrar**.  

16. En Internet Explorer, abra el sitio de SharePoint **http://localhost/sites/bassite/templates**.  

17. Seleccione  **\<MessageType\>**, haga clic en la flecha abajo situada junto a ella y, a continuación, haga clic en **editar propiedades**.  

18. En las plantillas:\< MessageType\> ventana, en el cuadro Namespace:  

    - Si va a generar los formularios de InfoPath MT, escriba: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**  

    - Si va a generar formularios MX de InfoPath, escriba: <strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageName\></strong>  

       Esto le ayudará a identificar la instancia de mensaje con la plantilla correspondiente.  

19. Haga clic en **guardar y cerrar**.
