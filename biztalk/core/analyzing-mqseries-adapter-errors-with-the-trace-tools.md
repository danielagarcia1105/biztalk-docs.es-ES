---
title: Analizar los errores de adaptador de MQSeries con las herramientas de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, about Adapter Trace Utility
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- errors, MQSeries adapters
- MQSeries adapters, Adapter Trace Utility
- Adapter Trace Utility, running
- MQSeries adapters, errors
- Adapter Trace Utility
ms.assetid: fdc73d99-3b73-491d-9b2f-7064364fefa7
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b53d1d2c0bbe19c54804b553041f8dc9ae4db20c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="analyzing-mqseries-adapter-errors-with-the-trace-tools"></a><span data-ttu-id="803dc-102">Analizar los errores de adaptador de MQSeries con las herramientas de seguimiento</span><span class="sxs-lookup"><span data-stu-id="803dc-102">Analyzing MQSeries Adapter Errors with the Trace Tools</span></span>
<span data-ttu-id="803dc-103">Las herramientas de seguimiento sirven para analizar errores de mensajería al ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="803dc-103">You use the trace tools to analyze messaging failures when you run your application.</span></span> <span data-ttu-id="803dc-104">El adaptador de MQSeries debe usarse conjuntamente con dos herramientas: una para el adaptador y la aplicación de BizTalk (trace.cmd), y la otra para MQSAgent (MQSTrace.cmd).</span><span class="sxs-lookup"><span data-stu-id="803dc-104">With the MQSeries adapter you must use two tools, one for the adapter and your BizTalk application (trace.cmd), and the other for the MQSAgent (MQSTrace.cmd).</span></span> <span data-ttu-id="803dc-105">Ambas herramientas utilizan tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="803dc-105">Both tools use tracelog.exe.</span></span> <span data-ttu-id="803dc-106">Tendrá que instalar tracelog.exe si no lo tiene.</span><span class="sxs-lookup"><span data-stu-id="803dc-106">You have to install tracelog.exe if you do not already have it.</span></span>  
  
 <span data-ttu-id="803dc-107">Con tanto en trace.cmd como en MQSTrace.cmd tiene que establecer una opción (**-herramientas**) para que estas herramientas puedan encontrar el archivo tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="803dc-107">With both trace.cmd and MQSTrace.cmd you have to set an option (**-tools**) so that these tools can find the tracelog.exe file.</span></span>  
  
## <a name="install-the-trace-utility"></a><span data-ttu-id="803dc-108">Instalar la Utilidad de seguimiento</span><span class="sxs-lookup"><span data-stu-id="803dc-108">Install the Trace Utility</span></span>  
 <span data-ttu-id="803dc-109">Siga este procedimiento para instalar la herramienta Utilidad de seguimiento del adaptador de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="803dc-109">To install the BizTalk Adapter Trace Utility, follow these steps:</span></span>  
  
1.  <span data-ttu-id="803dc-110">Para descargar el archivo Tracelog.exe, visite el sitio Web de descarga de Microsoft Platform SDK en [ http://go.microsoft.com/fwlink/?LinkId=21975 ](http://go.microsoft.com/fwlink/?LinkId=21975).</span><span class="sxs-lookup"><span data-stu-id="803dc-110">To download the Tracelog.exe file, visit the Microsoft Platform SDK download Web site at [http://go.microsoft.com/fwlink/?LinkId=21975](http://go.microsoft.com/fwlink/?LinkId=21975).</span></span>  
  
2.  <span data-ttu-id="803dc-111">Inicie el programa de instalación Web de Platform SDK haciendo clic en el vínculo para la **PSDK-x86.exe** archivo en la parte inferior de la página Web.</span><span class="sxs-lookup"><span data-stu-id="803dc-111">Start the Platform SDK Web installation program by clicking the link for the **PSDK-x86.exe** file at the bottom of the Web page.</span></span>  
  
3.  <span data-ttu-id="803dc-112">Cuando así lo solicite el programa, seleccione la opción de instalación personalizada.</span><span class="sxs-lookup"><span data-stu-id="803dc-112">When you are prompted, choose the option for a custom installation.</span></span>  
  
4.  <span data-ttu-id="803dc-113">En el cuadro de diálogo **Custom Installation** , haga clic hasta deshabilitar todas las características disponibles.</span><span class="sxs-lookup"><span data-stu-id="803dc-113">In the **Custom Installation** dialog box, click to clear all the available features.</span></span>  
  
5.  <span data-ttu-id="803dc-114">Expanda la característica **Microsoft Windows Core SDK** y, a continuación, expanda la característica **Tools** .</span><span class="sxs-lookup"><span data-stu-id="803dc-114">Expand the **Microsoft Windows Core SDK** feature, and then expand the **Tools** feature.</span></span>  
  
6.  <span data-ttu-id="803dc-115">Seleccione la característica **Tools (Intel 64-bit)** y, a continuación, haga clic en **Will be installed on local hard drive**.</span><span class="sxs-lookup"><span data-stu-id="803dc-115">Choose the **Tools (Intel 64-bit)** feature, and then click **Will be installed on local hard drive**.</span></span>  
  
7.  <span data-ttu-id="803dc-116">Haga clic en **Next**y de nuevo en **Next** para iniciar la instalación.</span><span class="sxs-lookup"><span data-stu-id="803dc-116">Click **Next**, and then click **Next** again to start the installation.</span></span>  
  
8.  <span data-ttu-id="803dc-117">Busque la *unidad*:\\*MicrosoftPlatformSDKInstallationFolder\bin* carpeta y, a continuación, copie el archivo Tracelog.exe file en la carpeta de instalación de Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="803dc-117">Locate the *drive*:\\*MicrosoftPlatformSDKInstallationFolder\bin* folder, and then copy the Tracelog.exe file to the Microsoft BizTalk Server installation folder.</span></span> <span data-ttu-id="803dc-118">El directorio de instalación de BizTalk Server contiene también el archivo Trace.cmd.</span><span class="sxs-lookup"><span data-stu-id="803dc-118">The BizTalk Server installation folder also contains the Trace.cmd file.</span></span>  
  
## <a name="enable-the-trace-utility"></a><span data-ttu-id="803dc-119">Habilitar la Utilidad de seguimiento</span><span class="sxs-lookup"><span data-stu-id="803dc-119">Enable the Trace Utility</span></span>  
 <span data-ttu-id="803dc-120">Siga este procedimiento para habilitar la herramienta Utilidad de seguimiento del adaptador de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="803dc-120">To enable the BizTalk Adapter Trace Utility in BizTalk Server, follow these steps:</span></span>  
  
1.  <span data-ttu-id="803dc-121">Ir al directorio que contiene trace.cmd.</span><span class="sxs-lookup"><span data-stu-id="803dc-121">Move to the directory that contains trace.cmd.</span></span> <span data-ttu-id="803dc-122">La ubicación predeterminada es el directorio de Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="803dc-122">The default location is the Microsoft BizTalk Server directory.</span></span>  
  
2.  <span data-ttu-id="803dc-123">Escriba el siguiente comando, sustituya el directorio que contiene el archivo tracelog.exe file en su PC por el directorio que está entre comillas y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="803dc-123">Type the following command, substituting the directory that contains the tracelog.exe file on your computer for the directory in quotes, and then press ENTER:</span></span>  
  
     <span data-ttu-id="803dc-124">**Trace - tools "c:\Program Files\Microsoft SDK\Bin"**</span><span class="sxs-lookup"><span data-stu-id="803dc-124">**trace -tools "c:\Program Files\Microsoft SDK\Bin"**</span></span>  
  
3.  <span data-ttu-id="803dc-125">Desplácese hasta el directorio que contenga el archivo MQSTrace.cmd.</span><span class="sxs-lookup"><span data-stu-id="803dc-125">Move to the directory that contains MQSTrace.cmd.</span></span>  
  
4.  <span data-ttu-id="803dc-126">Escriba el siguiente comando, sustituya el directorio que contiene el archivo tracelog.exe file en su PC por el directorio que está entre comillas y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="803dc-126">Type the following command, substituting the directory that contains the tracelog.exe file on your computer for the directory in quotes, and then press ENTER:</span></span>  
  
     <span data-ttu-id="803dc-127">**MQSTrace-tools "c:\Program Files\Microsoft SDK\Bin"**</span><span class="sxs-lookup"><span data-stu-id="803dc-127">**MQSTrace -tools "c:\Program Files\Microsoft SDK\Bin"**</span></span>  
  
## <a name="run-the-trace-utility"></a><span data-ttu-id="803dc-128">Ejecutar la Utilidad de seguimiento</span><span class="sxs-lookup"><span data-stu-id="803dc-128">Run the Trace Utility</span></span>  
 <span data-ttu-id="803dc-129">Siga este procedimiento para ejecutar la Utilidad de seguimiento del adaptador de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="803dc-129">To run the BizTalk Adapter Trace Utility, follow these steps:</span></span>  
  
1.  <span data-ttu-id="803dc-130">En el símbolo del sistema, escriba **trace.cmd-start - high**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="803dc-130">At the command prompt, type **trace.cmd -start -high**, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="803dc-131">Ejecute la situación de error.</span><span class="sxs-lookup"><span data-stu-id="803dc-131">Run your failure scenario.</span></span>  
  
3.  <span data-ttu-id="803dc-132">En el símbolo del sistema, escriba **trace.cmd-stop**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="803dc-132">At the command prompt, type **trace.cmd -stop**, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="803dc-133">El archivo bts2006.bin contiene la salida de la herramienta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="803dc-133">The bts2006.bin file contains the output of the trace tool.</span></span> <span data-ttu-id="803dc-134">Póngase en contacto con los servicios de soporte técnico de Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="803dc-134">Contact Microsoft Product Support Services for analysis.</span></span> <span data-ttu-id="803dc-135">Para obtener más información, consulte [ http://go.microsoft.com/fwlink/?LinkId=41645 ](http://go.microsoft.com/fwlink/?LinkId=41645).</span><span class="sxs-lookup"><span data-stu-id="803dc-135">For more information, see [http://go.microsoft.com/fwlink/?LinkId=41645](http://go.microsoft.com/fwlink/?LinkId=41645).</span></span>  
  
 <span data-ttu-id="803dc-136">Siga este procedimiento para ejecutar la Utilidad de seguimiento de MQSAgent:</span><span class="sxs-lookup"><span data-stu-id="803dc-136">To run the MQSAgent Trace Utility, follow these steps:</span></span>  
  
1.  <span data-ttu-id="803dc-137">En el símbolo del sistema, escriba **MQSTrace.cmd-start - high**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="803dc-137">At the command prompt, type **MQSTrace.cmd -start -high**, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="803dc-138">Ejecute la situación de error.</span><span class="sxs-lookup"><span data-stu-id="803dc-138">Run your failure scenario.</span></span>  
  
3.  <span data-ttu-id="803dc-139">En el símbolo del sistema, escriba **MQSTrace.cmd-stop**.</span><span class="sxs-lookup"><span data-stu-id="803dc-139">At the command prompt, type **MQSTrace.cmd -stop**.</span></span>  
  
4.  <span data-ttu-id="803dc-140">El archivo MQSAdapterTrace.bin contiene la salida de la herramienta de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="803dc-140">The MQSAdapterTrace.bin file contains the output of the trace tool.</span></span> <span data-ttu-id="803dc-141">Póngase en contacto con los servicios de soporte técnico de Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="803dc-141">Contact Microsoft Product Support Services for analysis.</span></span> <span data-ttu-id="803dc-142">Para obtener más información, consulte [ http://go.microsoft.com/fwlink/?LinkId=41645 ](http://go.microsoft.com/fwlink/?LinkId=41645).</span><span class="sxs-lookup"><span data-stu-id="803dc-142">For more information see [http://go.microsoft.com/fwlink/?LinkId=41645](http://go.microsoft.com/fwlink/?LinkId=41645).</span></span>