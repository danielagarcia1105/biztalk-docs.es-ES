---
title: Instalar el ejemplo de componente MQRFH2 de JMS | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5bd855-512f-40a4-8038-ae9b847b1097
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f04067ef6b2e1a057edc05601059d931b7ba7f28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018605"
---
# <a name="installing-the-jms-mqrfh2-component-sample"></a>Instalar el ejemplo de componente MQRFH2 de JMS
Para utilizar este ejemplo con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], también debe instalar lo siguiente:  
  
- IBM WebSphere MQ 5.3 (con CSD12), WebSphere MQ 6.x o WebSphere MQ 7.0  
  
- Utilidad para la puesta en cola y recuperar los mensajes de prueba de IBM "RfhUtil" JMS  
  
  El ejemplo del componente MQRFH2 de JMS requiere el componente MQRFH2 de JMS residen en la carpeta PipelineComponents de la carpeta de instalación de Microsoft BizTalk Server y los esquemas correspondientes a residen en la caché global de ensamblados. Instalar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core copia automáticamente y los ensamblados se instalan en las ubicaciones correctas. Sin embargo, si es necesario, se pueden realizar estas tareas manualmente.  
  
  **Para instalar manualmente el componente MQRFH2 de JMS y esquemas**  
  
1. Copie el ensamblado Microsoft.Practices.ESB.JMS.PipelineComponents.dll en la carpeta PipelineComponents de la carpeta de instalación de BizTalk Server.  
  
2. Agregar el ensamblado de esquema Microsoft.Practices.ESB.JMS.Schemas.Property.dll a la caché global de ensamblados mediante la herramienta de configuración de .NET Framework se encuentra en la sección de herramientas administrativas de la **iniciar** menú.  
  
   En esta sección se describe el proceso de instalación del ejemplo de MQRFH2 de JMS en la aplicación de GlobalBank.JMS BizTalk. Antes de instalar este ejemplo, debe instalar el núcleo del Kit de herramientas ESB como se describe en [instalar el núcleo de BizTalk ESB Toolkit](http://go.microsoft.com/fwlink/?LinkId=187612) ([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612)).  
  
   Puede instalar el ejemplo del componente MQRFH2 de JMS desde el proyecto de solución o usar el archivo de Windows Installer que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. Esta sección contiene los siguientes temas:  
  
-   [Instalar el ejemplo de MQRFH2 de JMS mediante los scripts de instalación](../esb-toolkit/install-the-jms-mqrfh2-sample-using-the-install-scripts.md)  
  
-   [Ensamblados y artefactos instalados por el ejemplo de componente MQRFH2 de JMS](../esb-toolkit/assemblies-and-artifacts-installed-by-the-jms-mqrfh2-component-sample.md)  
  
-   [Probar la instalación del ejemplo de MQRFH2 de JMS](../esb-toolkit/test-the-jms-mqrfh2-sample-installation.md)