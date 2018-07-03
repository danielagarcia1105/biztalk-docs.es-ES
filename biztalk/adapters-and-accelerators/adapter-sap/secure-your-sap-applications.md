---
title: Proteger las aplicaciones de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security and protection
ms.assetid: 9f0fb2a2-d6e2-4561-8472-c0bf682a4798
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dade1433b0bd432b53e48da86d53d23be7512de7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005789"
---
# <a name="secure-your-sap-applications"></a><span data-ttu-id="48138-102">Proteger las aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="48138-102">Secure your SAP applications</span></span>
<span data-ttu-id="48138-103">El sistema SAP puede contener información empresarial confidencial, como los detalles de la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="48138-103">The SAP system can contain sensitive business information such as customer account details.</span></span> <span data-ttu-id="48138-104">Las aplicaciones que usan el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida podría accidentalmente exponerla para tener acceso a los actores no autorizado, a menos que se realizan los esfuerzos para proteger y asegurar los datos durante transmisión.</span><span class="sxs-lookup"><span data-stu-id="48138-104">Applications that use the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="48138-105">Seguridad y protección de datos normalmente son pensar en los siguientes términos:</span><span class="sxs-lookup"><span data-stu-id="48138-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="48138-106">*Autorización* controla el acceso a un recurso basado en la identidad del solicitante.</span><span class="sxs-lookup"><span data-stu-id="48138-106">*Authorization* controls access to a resource based on the identity of the requestor.</span></span>  
  
- <span data-ttu-id="48138-107">*Autenticación* proporciona mecanismos para comprobar la identidad del solicitante.</span><span class="sxs-lookup"><span data-stu-id="48138-107">*Authentication* provides mechanisms for verifying the identity of a requestor.</span></span>  
  
- <span data-ttu-id="48138-108">*Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.</span><span class="sxs-lookup"><span data-stu-id="48138-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="48138-109">*Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, para que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.</span><span class="sxs-lookup"><span data-stu-id="48138-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="48138-110">Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que se desarrollan con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48138-110">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48138-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="48138-111">In this section</span></span>  
  
-   [<span data-ttu-id="48138-112">Seguridad entre el sistema de SAP y el adaptador</span><span class="sxs-lookup"><span data-stu-id="48138-112">Security between the SAP system and the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)
  
-   [<span data-ttu-id="48138-113">Seguridad con el adaptador de SAP y BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="48138-113">Security with the SAP adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)
  
-   [<span data-ttu-id="48138-114">Programación segura con el adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="48138-114">Secure programming with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)
  
-   [<span data-ttu-id="48138-115">Procedimientos recomendados para proteger el adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="48138-115">Best practices to secure the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)