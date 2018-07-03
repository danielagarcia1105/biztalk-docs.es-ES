---
title: Instalación del ejemplo de operaciones de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57c982c2-f796-4c63-9bca-7e8965779850
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a4fa6aeb56c9d5e4ed65e80f0a43c2cdedcf8b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002581"
---
# <a name="installing-the-biztalk-operations-sample"></a><span data-ttu-id="ffbbe-102">Instalación del ejemplo de operaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ffbbe-102">Installing the BizTalk Operations Sample</span></span>
<span data-ttu-id="ffbbe-103">El ejemplo de operaciones de Microsoft BizTalk requiere el servicio de operaciones de BizTalk ESB instalado y configurado.</span><span class="sxs-lookup"><span data-stu-id="ffbbe-103">The Microsoft BizTalk Operations sample requires the ESB BizTalk Operations service installed and configured.</span></span> <span data-ttu-id="ffbbe-104">Servicio de operaciones de BizTalk ESB es uno de los servicios Web de principales que se pueden instalar y configuran mediante la herramienta de configuración de ESB.</span><span class="sxs-lookup"><span data-stu-id="ffbbe-104">ESB BizTalk Operations service is one of the core Web services that can be installed and configured using the ESB Configuration Tool.</span></span> <span data-ttu-id="ffbbe-105">Para obtener más información sobre cómo usar la herramienta de configuración de ESB, consulte [ http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx ](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).</span><span class="sxs-lookup"><span data-stu-id="ffbbe-105">For more information about using the ESB Configuration Tool, see [http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).</span></span> <span data-ttu-id="ffbbe-106">La ubicación predeterminada del servicio Web de las operaciones de BizTalk es <http://localhost/ESB.BizTalkOperationsService/Operations.asmx>; sin embargo, puede cambiarlo en el archivo de configuración de aplicación si implementa el servicio en una ubicación diferente o un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="ffbbe-106">The default location of the BizTalk Operations Web service is <http://localhost/ESB.BizTalkOperationsService/Operations.asmx>; however, you can change this in the application configuration file if you deploy the service in a different location or a remote server.</span></span>  

 <span data-ttu-id="ffbbe-107">Debe instalar el ejemplo de operaciones de BizTalk desde el proyecto de solución.</span><span class="sxs-lookup"><span data-stu-id="ffbbe-107">You must install BizTalk Operations sample from the solution project.</span></span>  

 <span data-ttu-id="ffbbe-108">**Para instalar el ejemplo de operaciones de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="ffbbe-108">**To install the BizTalk Operations sample**</span></span>  

1. <span data-ttu-id="ffbbe-109">Abra la solución denominada ESB.BizTalkOperations.Test.Client.csproj desde la carpeta \Source\Samples\BizTalkOperations donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ffbbe-109">Open the solution named ESB.BizTalkOperations.Test.Client.csproj from the \Source\Samples\BizTalkOperations folder where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples into Visual Studio.</span></span>  

2. <span data-ttu-id="ffbbe-110">Use los comandos en el **compilar** menú para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="ffbbe-110">Use the commands on the **Build** menu to compile the solution.</span></span>
