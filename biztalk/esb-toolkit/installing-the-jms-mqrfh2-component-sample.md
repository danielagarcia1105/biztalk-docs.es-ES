---
title: Instalar el ejemplo de componente JMS MQRFH2 | Documentos de Microsoft
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
ms.openlocfilehash: 7b522d986524c77a53cf5a847f749a9ce41e2c50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294252"
---
# <a name="installing-the-jms-mqrfh2-component-sample"></a>Instalar el ejemplo de componente JMS MQRFH2
Para utilizar este ejemplo con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], también debe instalar lo siguiente:  
  
-   IBM WebSphere MQ 5.3 (con CSD12), WebSphere MQ 6.x o WebSphere MQ 7.0  
  
-   Utilidad de puesta en cola y recuperar los mensajes de prueba de la "RfhUtil" JMS de IBM  
  
 El ejemplo del componente de JMS MQRFH2 requiere el componente de JMS MQRFH2 residir en la carpeta PipelineComponents de la carpeta de instalación de Microsoft BizTalk Server y los esquemas correspondientes a residen en la caché global de ensamblados. Instalar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core copia automáticamente y los ensamblados se instalan en las ubicaciones correctas. Sin embargo, si es necesario, puede realizar manualmente estas tareas.  
  
 **Para instalar manualmente el componente de JMS MQRFH2 y esquemas**  
  
1.  Copie el ensamblado Microsoft.Practices.ESB.JMS.PipelineComponents.dll en la carpeta PipelineComponents de la carpeta de instalación de BizTalk Server.  
  
2.  Agregue el ensamblado de esquema Microsoft.Practices.ESB.JMS.Schemas.Property.dll a la caché de ensamblados global mediante la herramienta de configuración de .NET Framework se encuentra en la sección de herramientas administrativas de la **iniciar** menú.  
  
 Esta sección describe el proceso de instalación del ejemplo de JMS MQRFH2 en la aplicación de GlobalBank.JMS BizTalk. Antes de instalar este ejemplo, debe instalar el núcleo del Kit de herramientas ESB como se describe en [instalar el núcleo de Kit de herramientas de ESB de BizTalk](http://go.microsoft.com/fwlink/?LinkId=187612) ([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612)).  
  
 Puede instalar el ejemplo del componente de MQRFH2 de JMS desde el proyecto de la solución o usar el archivo de Windows Installer incluido con la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. Esta sección contiene los siguientes temas:  
  
-   [Instalar el ejemplo de MQRFH2 JMS mediante las secuencias de comandos de instalación](../esb-toolkit/install-the-jms-mqrfh2-sample-using-the-install-scripts.md)  
  
-   [Ensamblados y artefactos instalados en el ejemplo de componente JMS MQRFH2](../esb-toolkit/assemblies-and-artifacts-installed-by-the-jms-mqrfh2-component-sample.md)  
  
-   [Probar la instalación de ejemplo de MQRFH2 JMS](../esb-toolkit/test-the-jms-mqrfh2-sample-installation.md)