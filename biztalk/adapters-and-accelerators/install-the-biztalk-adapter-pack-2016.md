---
title: Instalar BizTalk Adapter Pack 2016 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23c74470-6336-49be-95c3-32b5c279e0ab
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fec17ce2da0183b9029839d3054261c5db3952a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="e9b2c-102">Instalar BizTalk Adapter Pack 2016</span><span class="sxs-lookup"><span data-stu-id="e9b2c-102">Install the BizTalk Adapter Pack 2016</span></span>
## <a name="overview"></a><span data-ttu-id="e9b2c-103">Información general</span><span class="sxs-lookup"><span data-stu-id="e9b2c-103">Overview</span></span>

<span data-ttu-id="e9b2c-104">El [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] (BAP) se incluye con [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9b2c-104">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] (BAP) is included with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e9b2c-105">Así, cuando descargue [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], también está descargando los adaptadores en el [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9b2c-105">So when you download [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], you are also downloading the adapters in the [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)].</span></span> 

<span data-ttu-id="e9b2c-106">El [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] utiliza el [!INCLUDE[firstref_btsWinCommFoundation_md](../includes/firstref-btswincommfoundation-md.md)] para comunicarse con sistemas de línea de negocio (LOB) de empresa diferente.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-106">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] uses the [!INCLUDE[firstref_btsWinCommFoundation_md](../includes/firstref-btswincommfoundation-md.md)] to communicate with different enterprise line-of-business (LOB) systems.</span></span> <span data-ttu-id="e9b2c-107">El [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] tiene su propio conjunto de requisitos, su propia experiencia de instalación y sus propios pasos de instalación.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-107">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] has its own set of requirements, its own setup experience, and its own installation steps.</span></span> 

<span data-ttu-id="e9b2c-108">El [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] es opcional y solo es necesario si desea [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] para enviar o recibir mensajes a cualquiera de los siguientes sistemas LOB de enterprise:</span><span class="sxs-lookup"><span data-stu-id="e9b2c-108">The [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] is optional, and is only needed if you want [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to send or receive messages to any of the following enterprise LOB systems:</span></span> 

* <span data-ttu-id="e9b2c-109">Base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="e9b2c-109">Oracle Database</span></span>
* <span data-ttu-id="e9b2c-110">Oracle E-Business Suite (EBS)</span><span class="sxs-lookup"><span data-stu-id="e9b2c-110">Oracle E-Business Suite (EBS)</span></span>
* <span data-ttu-id="e9b2c-111">SAP</span><span class="sxs-lookup"><span data-stu-id="e9b2c-111">SAP</span></span>
* <span data-ttu-id="e9b2c-112">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9b2c-112">SQL Server</span></span>
* <span data-ttu-id="e9b2c-113">Siebel</span><span class="sxs-lookup"><span data-stu-id="e9b2c-113">Siebel</span></span>

<span data-ttu-id="e9b2c-114">Todas las versiones de [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] incluye su propio [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] versión.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-114">Every version of [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] includes its own [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)] version.</span></span> <span data-ttu-id="e9b2c-115">Solo la versión incluida con su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versión es compatible.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-115">Only the version included with your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] version is supported.</span></span> <span data-ttu-id="e9b2c-116">No son compatibles con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="e9b2c-116">They are not backward-compatible.</span></span>

<span data-ttu-id="e9b2c-117">Este documento enumeran los requisitos de software y los pasos para instalar el módulo de adaptador de BizTalk (BAP) Microsoft incluido con [!INCLUDE[bts2016_md](../includes/bts2016-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9b2c-117">This document lists the software requirements, and the steps to install the Microsoft BizTalk Adapter Pack (BAP) included with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)].</span></span> 

## <a name="get-started-here"></a><span data-ttu-id="e9b2c-118">Empiece a trabajar aquí</span><span class="sxs-lookup"><span data-stu-id="e9b2c-118">Get started here</span></span>
[<span data-ttu-id="e9b2c-119">Requisitos previos de software</span><span class="sxs-lookup"><span data-stu-id="e9b2c-119">Software prerequisites</span></span>](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="e9b2c-120">Pasos de la instalación</span><span class="sxs-lookup"><span data-stu-id="e9b2c-120">Install steps</span></span>](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="e9b2c-121">Pasos posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="e9b2c-121">Post installation steps</span></span>](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="e9b2c-122">Actualizar o desinstalar</span><span class="sxs-lookup"><span data-stu-id="e9b2c-122">Update or uninstall</span></span>](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)