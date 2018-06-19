---
title: La clase MapHelper | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c552c066-835f-4515-939f-dd465a7a5ed0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de74610c40b37560abcbce040d80320525f0a21c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295116"
---
# <a name="the-maphelper-class"></a><span data-ttu-id="45f4c-102">La clase MapHelper</span><span class="sxs-lookup"><span data-stu-id="45f4c-102">The MapHelper Class</span></span>
<span data-ttu-id="45f4c-103">Use la **MapHelper** clase para realizar transformaciones directamente sin usar la transformación del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="45f4c-103">Use the **MapHelper** class to perform transformations directly without using the transformation Web service.</span></span>  
  
 <span data-ttu-id="45f4c-104">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] instalador instala y registra el ensamblado **Microsof.Practices.ESB.Transform.dll** con el **MapHelper** clase en la memoria caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="45f4c-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] installer installs and registers the assembly **Microsof.Practices.ESB.Transform.dll** with the **MapHelper** class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="45f4c-105">El **MapHelper** clase expone dos métodos públicos:</span><span class="sxs-lookup"><span data-stu-id="45f4c-105">The **MapHelper** class exposes two public methods:</span></span>  
  
-   <span data-ttu-id="45f4c-106">**TransformMessage**.</span><span class="sxs-lookup"><span data-stu-id="45f4c-106">**TransformMessage**.</span></span> <span data-ttu-id="45f4c-107">Este método toma como parámetros de una cadena que contiene el mensaje que se va a transformar y una cadena que contiene el nombre completo de un mapa que se implementan en BizTalk.</span><span class="sxs-lookup"><span data-stu-id="45f4c-107">This method takes as parameters a string that contains the message to transform and a string that contains the fully qualified name of a map deployed in BizTalk.</span></span> <span data-ttu-id="45f4c-108">El método devuelve una cadena que contiene el documento transformado.</span><span class="sxs-lookup"><span data-stu-id="45f4c-108">The method returns a string containing the transformed document.</span></span>  
  
-   <span data-ttu-id="45f4c-109">**TransformMessageStream**.</span><span class="sxs-lookup"><span data-stu-id="45f4c-109">**TransformMessageStream**.</span></span> <span data-ttu-id="45f4c-110">Este método toma como parámetros de una secuencia que contiene el mensaje que se va a transformar y una cadena que contiene el nombre completo de un mapa que se implementan en BizTalk.</span><span class="sxs-lookup"><span data-stu-id="45f4c-110">This method takes as parameters a stream that contains the message to transform and a string that contains the fully qualified name of a map deployed in BizTalk.</span></span> <span data-ttu-id="45f4c-111">El método devuelve una cadena que contiene el documento transformado.</span><span class="sxs-lookup"><span data-stu-id="45f4c-111">The method returns a string that contains the transformed document.</span></span>