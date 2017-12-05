---
title: "Publicar el archivo de instancia de mensaje MX (creación de nuevos mensajes) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7e6cdf4-b9db-42be-a92d-10a7471e2c2d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4082174428f177905527d0c648b4d7ad000dde36
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="publishing-the-mx-message-instance-file-creating-new-messages"></a><span data-ttu-id="d89c8-102">Publicar el archivo de instancia de mensaje MX (creación de nuevos mensajes)</span><span class="sxs-lookup"><span data-stu-id="d89c8-102">Publishing the MX Message Instance File (Creating New Messages)</span></span>
<span data-ttu-id="d89c8-103">**Para publicar el archivo de instancia de mensaje MX:**</span><span class="sxs-lookup"><span data-stu-id="d89c8-103">**To publish the MX message instance file:**</span></span>  
  
1.  <span data-ttu-id="d89c8-104">Vaya a la carpeta de salida de la plantilla de formulario de InfoPath que generó en el paso anterior **... \\< MessageType\>plantilla de formulario de \TemplateDS\InfoPath**.</span><span class="sxs-lookup"><span data-stu-id="d89c8-104">Go to output folder of the InfoPath form template generated in the previous step **..\\<MessageType\>\TemplateDS\InfoPath Form Template**.</span></span>  
  
2.  <span data-ttu-id="d89c8-105">En Internet Explorer, abra **http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**.</span><span class="sxs-lookup"><span data-stu-id="d89c8-105">In Internet Explorer, open **http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**.</span></span>  
  
3.  <span data-ttu-id="d89c8-106">En la ventana de nuevos mensajes de Swift MX, haga clic en **cargar**.</span><span class="sxs-lookup"><span data-stu-id="d89c8-106">In New Swift MX Messages window, click **Upload**.</span></span>  
  
4.  <span data-ttu-id="d89c8-107">En la ventana Cargar documento, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="d89c8-107">In the Upload Document window, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="d89c8-108">En el cuadro de diálogo Elegir archivo, desplácese a la carpeta de salida del formulario de InfoPath que se generó en el paso anterior **... \\< MessageType\>plantilla de formulario de \TemplateDS\InfoPath**.</span><span class="sxs-lookup"><span data-stu-id="d89c8-108">In the Choose file dialog box, move to the output folder of the InfoPath form generated in the previous step **..\\<MessageType\>\TemplateDS\InfoPath Form Template**.</span></span> <span data-ttu-id="d89c8-109">Seleccione el \<MessageType\>como pacs.004.001.01.xml de archivos .xml y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="d89c8-109">Select the \<MessageType\>.xml file such as pacs.004.001.01.xml, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="d89c8-110">En la ventana Cargar documento, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d89c8-110">In the Upload Document window, click **OK**.</span></span>  
  
7.  <span data-ttu-id="d89c8-111">En los mensajes de nuevo MX SWIFT: \<MessageType\> ventana, en el cuadro de Namespace, escriba **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX _\<MessageType\>** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d89c8-111">In the New SWIFT MX Messages: \<MessageType\> window, in the Namespace box, type **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageType\>**, and then click **OK**.</span></span>