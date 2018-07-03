---
title: Prequisities para los tutoriales del SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7d47ac1-1605-4c6d-a331-8583771dca28
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9e0f1959563b0a0f1273de6341e2402f90f8f34
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995453"
---
# <a name="prequisities-for-the-wcf-lob-adapter-sdk-tutorials"></a><span data-ttu-id="9e139-102">Prequisities para los tutoriales del SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="9e139-102">Prequisities for the WCF LOB Adapter SDK tutorials</span></span>
<span data-ttu-id="9e139-103">Esta sección proporciona detalles sobre los conceptos que debe estar familiarizado con para sacar el máximo partido de los tutoriales, así como el software necesario para realizarlas.</span><span class="sxs-lookup"><span data-stu-id="9e139-103">This section provides details about the concepts you should be familiar with to get the most out of the tutorials, as well as the software required to complete them.</span></span>  
  
## <a name="what-to-install"></a><span data-ttu-id="9e139-104">¿Qué ocurre al instalar</span><span class="sxs-lookup"><span data-stu-id="9e139-104">What to Install</span></span>  
 <span data-ttu-id="9e139-105">Para iniciar los tutoriales, debe tener el siguiente software instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9e139-105">To start the tutorials, you must have the following software installed on your computer.</span></span>  
  
- [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]
  
- <span data-ttu-id="9e139-106">Servicios de Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="9e139-106">Internet Information Services (IIS)</span></span>  
  
- [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]
  
- [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<span data-ttu-id="9e139-107"> (disponible con los archivos de instalación de BizTalk Server y con nombre ASDK_x64 y ASDK_x86)</span><span class="sxs-lookup"><span data-stu-id="9e139-107"> (available with your BizTalk Server installation files, and named ASDK_x64 and ASDK_x86)</span></span>  
  
  <span data-ttu-id="9e139-108">Para completar el Tutorial 3, debe tener el siguiente software instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9e139-108">To complete Tutorial 3, you must have the following software installed on your computer.</span></span>  
  
- <span data-ttu-id="9e139-109">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="9e139-109">Microsoft SharePoint</span></span>  
  
- <span data-ttu-id="9e139-110">SDK de Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="9e139-110">Microsoft SharePoint SDK</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="9e139-111">No realice estos tutoriales en su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="9e139-111">Do not perform these tutorials in your production environment.</span></span>  
  
<span data-ttu-id="9e139-112">Se incluye con los archivos de instalación de BizTalk en el adaptador de Echo completado `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` o `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span><span class="sxs-lookup"><span data-stu-id="9e139-112">The completed Echo Adapter is included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="9e139-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e139-113">Prerequisites</span></span>  
 <span data-ttu-id="9e139-114">Los tutoriales se supone que está familiarizado con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e139-114">The tutorials assume that you are familiar with the following:</span></span>  
  
- <span data-ttu-id="9e139-115">Desarrollo y diseño de software orientada a objetos</span><span class="sxs-lookup"><span data-stu-id="9e139-115">Object-oriented software design and development</span></span>  
  
- <span data-ttu-id="9e139-116">Windows Communication Foundation (WCF), en concreto, programación de modelos del canal y programación del modelo de servicio</span><span class="sxs-lookup"><span data-stu-id="9e139-116">Windows Communication Foundation (WCF), specifically, channel model programming and service model programming</span></span>  
  
- <span data-ttu-id="9e139-117">La relación entre el lenguaje de descripción de servicios Web (WSDL) y una API, XML, WSDL y XSD</span><span class="sxs-lookup"><span data-stu-id="9e139-117">XSD, XML, WSDL, and the relationship between Web Services Description Language (WSDL) and an API</span></span>  
  
- <span data-ttu-id="9e139-118">Lenguaje de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9e139-118">C# programming language</span></span>  
  
- <span data-ttu-id="9e139-119">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="9e139-119">.NET Framework</span></span>  
  
  <span data-ttu-id="9e139-120">Antes de comenzar los tutoriales, también le resultará útil si ha revisado los temas conceptuales de este SDK y tiene una descripción general de los canales en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], incluidos los tipos dentro de la **T:Microsoft.ServiceModel.Channels**y **T:Microsoft.ServiceModel.Channels.Common** espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="9e139-120">Before starting the tutorials, it will be helpful if you have reviewed the conceptual topics of this SDK, and have a general understanding of channels in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], including the types within the **T:Microsoft.ServiceModel.Channels** and **T:Microsoft.ServiceModel.Channels.Common** namespaces.</span></span>  <span data-ttu-id="9e139-121">Para obtener más información acerca de los canales, consulte el [información general del modelo de canal](https://msdn.microsoft.com/library/ms729840.aspx).</span><span class="sxs-lookup"><span data-stu-id="9e139-121">For more information about channels, see the [Channel Model Overview](https://msdn.microsoft.com/library/ms729840.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e139-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e139-122">See Also</span></span>  
 [<span data-ttu-id="9e139-123">Tutoriales para obtener información sobre el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="9e139-123">Tutorials to learn the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)