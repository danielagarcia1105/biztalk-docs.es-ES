---
title: 'MSCIT: Uso de servicios de BizTalk de Microsoft Azure para pedidos de la cadena de suministro | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22091261-cd17-45b2-8746-dc174b52dcff
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6a1609be7326db4988d31d51597cde3fd280227
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mscit-using-microsoft-azure-biztalk-services-for-supply-chain-orders"></a><span data-ttu-id="60ae9-102">MSCIT: Uso de servicios de BizTalk de Microsoft Azure para pedidos de la cadena de suministro</span><span class="sxs-lookup"><span data-stu-id="60ae9-102">MSCIT: Using Microsoft Azure BizTalk Services for Supply Chain Orders</span></span>
<span data-ttu-id="60ae9-103">**Dispositivos de Microsoft & estudios: uso de servicios de BizTalk de Microsoft Azure para pedidos de la cadena de suministro**</span><span class="sxs-lookup"><span data-stu-id="60ae9-103">**Microsoft Devices & Studios: Using Microsoft Azure BizTalk Services for Supply Chain Orders**</span></span>  
  
 <span data-ttu-id="60ae9-104">Artículo técnico de BizTalk</span><span class="sxs-lookup"><span data-stu-id="60ae9-104">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="60ae9-105">**Escritor:** Anil Kongari (Microsoft), Dipti Sharma (Microsoft), Mandi Ohlinger (Microsoft)</span><span class="sxs-lookup"><span data-stu-id="60ae9-105">**Writer:** Anil Kongari (Microsoft), Dipti Sharma (Microsoft), Mandi Ohlinger (Microsoft)</span></span>  
  
 <span data-ttu-id="60ae9-106">**Revisores técnicos:** Anil Kongari (Microsoft), Hariharan Sundaram (Microsoft), Dipti Sharma (Microsoft), Heena Parmar (Microsoft)</span><span class="sxs-lookup"><span data-stu-id="60ae9-106">**Technical Reviewers:** Anil Kongari (Microsoft), Hariharan Sundaram (Microsoft), Dipti Sharma (Microsoft), Heena Parmar (Microsoft)</span></span>  
  
 <span data-ttu-id="60ae9-107">**Fecha de publicación:** octubre de 2013</span><span class="sxs-lookup"><span data-stu-id="60ae9-107">**Published:** October 2013</span></span>  
  
 <span data-ttu-id="60ae9-108">**Se aplica a:** servicios de BizTalk de Microsoft Azure (MABS) y BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="60ae9-108">**Applies To:** Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013</span></span>  
  
 <span data-ttu-id="60ae9-109">**Resumen:** el grupo de fabricación y cadena de suministro, servicios de información (MSCIS) es un grupo Global Supply Chain Management de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="60ae9-109">**Summary:** The Manufacturing, Supply Chain, and Information Services (MSCIS) group is a Global Supply Chain Management group at Microsoft.</span></span> <span data-ttu-id="60ae9-110">Cada año, Microsoft lanza nuevos productos.</span><span class="sxs-lookup"><span data-stu-id="60ae9-110">Every year, Microsoft launches new products.</span></span> <span data-ttu-id="60ae9-111">MSCIS es responsable de llevar estos nuevos productos al mercado.</span><span class="sxs-lookup"><span data-stu-id="60ae9-111">MSCIS is responsible for bringing these new products to market.</span></span> <span data-ttu-id="60ae9-112">Para admitir estos productos, se agregan nuevos socios a la cadena de suministro, incluidos los proveedores, fabricante, distribuidor, vendedor, centro de servicios, operador y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="60ae9-112">To support these products, new partners are added to the Supply Chain, including Supplier, Manufacturer, Distributor, Retailer, Service Center, Carrier, and so on.</span></span>  
  
 <span data-ttu-id="60ae9-113">Cada año, aumenta el número de transacciones asociado.</span><span class="sxs-lookup"><span data-stu-id="60ae9-113">The number of partner transactions increases yearly.</span></span> <span data-ttu-id="60ae9-114">Durante la carga alta, hay problemas relacionados con el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="60ae9-114">During high load, there are issues related to throughput.</span></span> <span data-ttu-id="60ae9-115">Mientras el concentrador de BizTalk de cadena de suministro procesa más transacciones (mayor volumen), no es capaz de mantener el sistema de servidor o el sistema de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="60ae9-115">While the Supply Chain BizTalk hub processes more transactions (increased volume), the end system or partner system is not able to keep up.</span></span>  
  
 <span data-ttu-id="60ae9-116">El desafío actual consiste en preparar los sistemas de negocio a negocio (B2B) para las ventas de pico.</span><span class="sxs-lookup"><span data-stu-id="60ae9-116">The current challenge is to prepare the business-to-business (B2B) systems for peak sales.</span></span> <span data-ttu-id="60ae9-117">Como parte del programa de adopción de tecnología (TAP), MSCIS está valorando plataforma como servicio (PaaS) mediante los servicios de BizTalk de Microsoft Azure (MABS).</span><span class="sxs-lookup"><span data-stu-id="60ae9-117">As part of Technology Adoption Program (TAP), MSCIS is exploring Platform as a Service (PaaS) using Microsoft Azure BizTalk Services (MABS).</span></span> <span data-ttu-id="60ae9-118">MABS proporciona capacidades clave que pueden resolver la situación de escala.</span><span class="sxs-lookup"><span data-stu-id="60ae9-118">MABS provides key capabilities that can solve the scale situation.</span></span> <span data-ttu-id="60ae9-119">MSCIS crea una prueba de concepto (POC) que implica una solución híbrida que usa servicios de BizTalk de Microsoft Azure (MABS) y BizTalk Server 2013.</span><span class="sxs-lookup"><span data-stu-id="60ae9-119">MSCIS created a Proof of Concept (POC) involving a hybrid solution that uses Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013.</span></span> <span data-ttu-id="60ae9-120">El requisito es ofrecer una ejecución perfecta desde to-end, incluida la capacidad para escalar hacia arriba para ventas de pico y escala hacia abajo para ventas normales.</span><span class="sxs-lookup"><span data-stu-id="60ae9-120">The requirement is to provide flawless execution from end-to-end, including the ability to scale up for peak sales and scale down for normal sales.</span></span>  
  
 <span data-ttu-id="60ae9-121">Estas notas del producto se describen las soluciones que se probó con servicios de BizTalk de Microsoft Azure (MABS) y BizTalk Server 2013.</span><span class="sxs-lookup"><span data-stu-id="60ae9-121">This white paper discusses the solutions tested using Microsoft Azure BizTalk Services (MABS) and BizTalk Server 2013.</span></span>  
  
 <span data-ttu-id="60ae9-122">Para revisar el documento, descargue el [utilizando los servicios de BizTalk de Microsoft Azure para pedidos de la cadena de suministros](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Using%20Windows%20Azure%20BizTalk%20Services%20for%20Supply%20Chain%20Orders.docx) documento de Word.</span><span class="sxs-lookup"><span data-stu-id="60ae9-122">To review the document, please download the [Using Microsoft Azure BizTalk Services for Supply Chain Orders](http://download.microsoft.com/download/6/D/E/6DEE8EE9-0F26-4991-8FE5-B0E5239C0980/Using%20Windows%20Azure%20BizTalk%20Services%20for%20Supply%20Chain%20Orders.docx) Word document.</span></span>