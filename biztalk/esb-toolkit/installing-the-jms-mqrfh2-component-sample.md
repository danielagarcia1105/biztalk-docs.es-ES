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
# <a name="installing-the-jms-mqrfh2-component-sample"></a><span data-ttu-id="0d242-102">Instalar el ejemplo de componente MQRFH2 de JMS</span><span class="sxs-lookup"><span data-stu-id="0d242-102">Installing the JMS MQRFH2 Component Sample</span></span>
<span data-ttu-id="0d242-103">Para utilizar este ejemplo con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], también debe instalar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d242-103">To use this sample with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], you must also install the following:</span></span>  
  
- <span data-ttu-id="0d242-104">IBM WebSphere MQ 5.3 (con CSD12), WebSphere MQ 6.x o WebSphere MQ 7.0</span><span class="sxs-lookup"><span data-stu-id="0d242-104">IBM WebSphere MQ 5.3 (with CSD12), WebSphere MQ 6.x or WebSphere MQ 7.0</span></span>  
  
- <span data-ttu-id="0d242-105">Utilidad para la puesta en cola y recuperar los mensajes de prueba de IBM "RfhUtil" JMS</span><span class="sxs-lookup"><span data-stu-id="0d242-105">The IBM "RfhUtil" JMS test utility for queuing and retrieving messages</span></span>  
  
  <span data-ttu-id="0d242-106">El ejemplo del componente MQRFH2 de JMS requiere el componente MQRFH2 de JMS residen en la carpeta PipelineComponents de la carpeta de instalación de Microsoft BizTalk Server y los esquemas correspondientes a residen en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0d242-106">The JMS MQRFH2 Component sample requires the JMS MQRFH2 component to reside in the PipelineComponents folder of your Microsoft BizTalk Server installation folder and the corresponding schemas to reside in the global assembly cache.</span></span> <span data-ttu-id="0d242-107">Instalar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core copia automáticamente y los ensamblados se instalan en las ubicaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="0d242-107">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the assemblies to the correct locations.</span></span> <span data-ttu-id="0d242-108">Sin embargo, si es necesario, se pueden realizar estas tareas manualmente.</span><span class="sxs-lookup"><span data-stu-id="0d242-108">However, if required, you can manually perform these tasks.</span></span>  
  
  <span data-ttu-id="0d242-109">**Para instalar manualmente el componente MQRFH2 de JMS y esquemas**</span><span class="sxs-lookup"><span data-stu-id="0d242-109">**To manually install the JMS MQRFH2 component and schemas**</span></span>  
  
1. <span data-ttu-id="0d242-110">Copie el ensamblado Microsoft.Practices.ESB.JMS.PipelineComponents.dll en la carpeta PipelineComponents de la carpeta de instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0d242-110">Copy the assembly Microsoft.Practices.ESB.JMS.PipelineComponents.dll to the PipelineComponents folder of your BizTalk Server installation folder.</span></span>  
  
2. <span data-ttu-id="0d242-111">Agregar el ensamblado de esquema Microsoft.Practices.ESB.JMS.Schemas.Property.dll a la caché global de ensamblados mediante la herramienta de configuración de .NET Framework se encuentra en la sección de herramientas administrativas de la **iniciar** menú.</span><span class="sxs-lookup"><span data-stu-id="0d242-111">Add the schema assembly Microsoft.Practices.ESB.JMS.Schemas.Property.dll to the global assembly cache using the .NET Framework Configuration Tool located in the Administrative Tools section of the **Start** menu.</span></span>  
  
   <span data-ttu-id="0d242-112">En esta sección se describe el proceso de instalación del ejemplo de MQRFH2 de JMS en la aplicación de GlobalBank.JMS BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0d242-112">This section describes the process for installing the JMS MQRFH2 sample into the GlobalBank.JMS BizTalk application.</span></span> <span data-ttu-id="0d242-113">Antes de instalar este ejemplo, debe instalar el núcleo del Kit de herramientas ESB como se describe en [instalar el núcleo de BizTalk ESB Toolkit](http://go.microsoft.com/fwlink/?LinkId=187612) ([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612)).</span><span class="sxs-lookup"><span data-stu-id="0d242-113">Before you install this sample, you must install the ESB Toolkit Core as described in [Installing the BizTalk ESB Toolkit Core](http://go.microsoft.com/fwlink/?LinkId=187612) ([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612)).</span></span>  
  
   <span data-ttu-id="0d242-114">Puede instalar el ejemplo del componente MQRFH2 de JMS desde el proyecto de solución o usar el archivo de Windows Installer que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d242-114">You can install the JMS MQRFH2 Component sample from the solution project or use the Windows Installer file included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="0d242-115">Esta sección contiene los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="0d242-115">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="0d242-116">Instalar el ejemplo de MQRFH2 de JMS mediante los scripts de instalación</span><span class="sxs-lookup"><span data-stu-id="0d242-116">Install the JMS MQRFH2 Sample Using the Install Scripts</span></span>](../esb-toolkit/install-the-jms-mqrfh2-sample-using-the-install-scripts.md)  
  
-   [<span data-ttu-id="0d242-117">Ensamblados y artefactos instalados por el ejemplo de componente MQRFH2 de JMS</span><span class="sxs-lookup"><span data-stu-id="0d242-117">Assemblies and Artifacts Installed by the JMS MQRFH2 Component Sample</span></span>](../esb-toolkit/assemblies-and-artifacts-installed-by-the-jms-mqrfh2-component-sample.md)  
  
-   [<span data-ttu-id="0d242-118">Probar la instalación del ejemplo de MQRFH2 de JMS</span><span class="sxs-lookup"><span data-stu-id="0d242-118">Test the JMS MQRFH2 Sample Installation</span></span>](../esb-toolkit/test-the-jms-mqrfh2-sample-installation.md)