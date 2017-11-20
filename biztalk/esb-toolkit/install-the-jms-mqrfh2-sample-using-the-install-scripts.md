---
title: "Instalar el ejemplo de MQRFH2 JMS con los Scripts de instalación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 785f3e32-83b4-406a-af1b-9499115fbb8f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27b3606d53f692ff52779eeac3505fd8062bed28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-jms-mqrfh2-sample-using-the-install-scripts"></a><span data-ttu-id="ae745-102">Instalar el ejemplo de MQRFH2 JMS mediante las secuencias de comandos de instalación</span><span class="sxs-lookup"><span data-stu-id="ae745-102">Install the JMS MQRFH2 Sample Using the Install Scripts</span></span>
<span data-ttu-id="ae745-103">En esta sección se describe cómo puede instalar el ejemplo de JMS MQRFH2 mediante los scripts de instalación que se proporcionan con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae745-103">This section describes how you can install the JMS MQRFH2 sample using the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="ae745-104">**Para instalar los ejemplos de JMS MQRFH2 desde las secuencias de comandos de instalación**</span><span class="sxs-lookup"><span data-stu-id="ae745-104">**To install the JMS MQRFH2 samples from the install scripts**</span></span>  
  
1.  <span data-ttu-id="ae745-105">Mediante el Explorador de WebSphere, cree un administrador de cola con el nombre **ESB. JMS. Sample.QueueManager**.</span><span class="sxs-lookup"><span data-stu-id="ae745-105">Using WebSphere Explorer, create a Queue Manager with the name **ESB.JMS.Sample.QueueManager**.</span></span>  
  
2.  <span data-ttu-id="ae745-106">Mediante el Explorador de WebSphere, cree las siguientes cuatro colas dentro de **ESB. JMS. Sample.QueueManager:**</span><span class="sxs-lookup"><span data-stu-id="ae745-106">Using WebSphere Explorer, create the following four queues within **ESB.JMS.Sample.QueueManager:**</span></span>  
  
    -   <span data-ttu-id="ae745-107">ESB. JMS. EJEMPLO. DYNAMICQ1</span><span class="sxs-lookup"><span data-stu-id="ae745-107">ESB.JMS.SAMPLE.DYNAMICQ1</span></span>  
  
    -   <span data-ttu-id="ae745-108">ESB. JMS. EJEMPLO. DYNAMICQ2</span><span class="sxs-lookup"><span data-stu-id="ae745-108">ESB.JMS.SAMPLE.DYNAMICQ2</span></span>  
  
    -   <span data-ttu-id="ae745-109">ESB. JMS. EJEMPLO. RESPUESTA</span><span class="sxs-lookup"><span data-stu-id="ae745-109">ESB.JMS.SAMPLE.REPLY</span></span>  
  
    -   <span data-ttu-id="ae745-110">ESB. JMS. EJEMPLO. SENDTOBIZTALK</span><span class="sxs-lookup"><span data-stu-id="ae745-110">ESB.JMS.SAMPLE.SENDTOBIZTALK</span></span>  
  
3.  <span data-ttu-id="ae745-111">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ae745-111">On the **Start** menu, click **Run**.</span></span>  
  
4.  <span data-ttu-id="ae745-112">En el **ejecutar** cuadro de diálogo, escriba **cmd**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ae745-112">In the **Run** dialog box, type **cmd**, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="ae745-113">Ejecute el comando siguiente, reemplazando el  *\<ruta de acceso >* parámetro con la ruta de acceso completa al archivo .cmd que desea instalar (la ruta predeterminada en esta versión es \Source\Samples\JMS\Install\Scripts\\):</span><span class="sxs-lookup"><span data-stu-id="ae745-113">Run the following command, replacing the *\<path>* parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\JMS\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```