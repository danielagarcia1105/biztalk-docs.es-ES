---
title: Proteger las aplicaciones de SAP | Documentos de Microsoft
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
ms.openlocfilehash: 49f5fe75acf7b033d0f957c7742f52ba521bdde7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216300"
---
# <a name="secure-your-sap-applications"></a><span data-ttu-id="2756a-102">Proteger las aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="2756a-102">Secure your SAP applications</span></span>
<span data-ttu-id="2756a-103">El sistema SAP puede contener la información empresarial confidencial, como los detalles de cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="2756a-103">The SAP system can contain sensitive business information such as customer account details.</span></span> <span data-ttu-id="2756a-104">Las aplicaciones que utilizan el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida puede accidentalmente exponerla obtener acceso a los actores no autorizados, a menos que se haga un esfuerzo para proteger y proteger los datos durante la transmisión.</span><span class="sxs-lookup"><span data-stu-id="2756a-104">Applications that use the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="2756a-105">Seguridad y protección de datos normalmente se considera de en los siguientes términos:</span><span class="sxs-lookup"><span data-stu-id="2756a-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
-   <span data-ttu-id="2756a-106">*Autorización* controla el acceso a un recurso basado en la identidad del solicitante.</span><span class="sxs-lookup"><span data-stu-id="2756a-106">*Authorization* controls access to a resource based on the identity of the requestor.</span></span>  
  
-   <span data-ttu-id="2756a-107">*Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.</span><span class="sxs-lookup"><span data-stu-id="2756a-107">*Authentication* provides mechanisms for verifying the identity of a requestor.</span></span>  
  
-   <span data-ttu-id="2756a-108">*Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.</span><span class="sxs-lookup"><span data-stu-id="2756a-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
-   <span data-ttu-id="2756a-109">*Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, por lo que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.</span><span class="sxs-lookup"><span data-stu-id="2756a-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
 <span data-ttu-id="2756a-110">Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que desarrolle con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2756a-110">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2756a-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2756a-111">In this section</span></span>  
  
-   [<span data-ttu-id="2756a-112">Seguridad entre el sistema SAP y el adaptador</span><span class="sxs-lookup"><span data-stu-id="2756a-112">Security between the SAP system and the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)
  
-   [<span data-ttu-id="2756a-113">Seguridad con el adaptador SAP y BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2756a-113">Security with the SAP adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)
  
-   [<span data-ttu-id="2756a-114">Programación segura con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="2756a-114">Secure programming with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)
  
-   [<span data-ttu-id="2756a-115">Prácticas recomendadas para proteger el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="2756a-115">Best practices to secure the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)