---
title: Proteger las aplicaciones de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security and protection
- data protection
ms.assetid: 8977cbd3-0025-48d4-8203-8e9e72ea7d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad63e44e4d2dde5ffee743e0758a37e48a3d4d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012061"
---
# <a name="secure-your-siebel-applications"></a><span data-ttu-id="9cd17-102">Proteger las aplicaciones de Siebel</span><span class="sxs-lookup"><span data-stu-id="9cd17-102">Secure your Siebel applications</span></span>
<span data-ttu-id="9cd17-103">El sistema de Siebel a menudo contiene información empresarial confidencial, como los detalles de la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="9cd17-103">The Siebel system often contains sensitive business information such as customer account details.</span></span> <span data-ttu-id="9cd17-104">Las aplicaciones que usan el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida podría accidentalmente exponerla para tener acceso a los actores no autorizado, a menos que se realizan los esfuerzos para proteger y asegurar los datos durante transmisión.</span><span class="sxs-lookup"><span data-stu-id="9cd17-104">Applications that use the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="9cd17-105">Seguridad y protección de datos normalmente son pensar en los siguientes términos:</span><span class="sxs-lookup"><span data-stu-id="9cd17-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="9cd17-106">*Autorización* controla el acceso a un recurso basado en la identidad del solicitante.</span><span class="sxs-lookup"><span data-stu-id="9cd17-106">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
- <span data-ttu-id="9cd17-107">*Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.</span><span class="sxs-lookup"><span data-stu-id="9cd17-107">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
- <span data-ttu-id="9cd17-108">*Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.</span><span class="sxs-lookup"><span data-stu-id="9cd17-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="9cd17-109">*Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, para que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.</span><span class="sxs-lookup"><span data-stu-id="9cd17-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="9cd17-110">Otra área importante de preocupación es las credenciales de contraseña de nombre de usuario que proporcione a los [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cd17-110">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="9cd17-111">El adaptador usa estas credenciales para abrir conexiones con el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="9cd17-111">The adapter uses these credentials to open connections to the Siebel system.</span></span> <span data-ttu-id="9cd17-112">Estas credenciales se pueden proporcionar en la conexión URI; Sin embargo, dado que el nombre de usuario y la contraseña son texto no cifrado, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] proporciona los métodos alternativos que puede usar para proporcionar estas credenciales en forma más segura.</span><span class="sxs-lookup"><span data-stu-id="9cd17-112">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
  <span data-ttu-id="9cd17-113">Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que se desarrollan con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cd17-113">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9cd17-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9cd17-114">In This Section</span></span>  
  
-   [<span data-ttu-id="9cd17-115">Seguridad entre el sistema de Siebel y el adaptador</span><span class="sxs-lookup"><span data-stu-id="9cd17-115">Security between the Siebel system and the adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/security-between-the-siebel-system-and-the-adapter.md)
  
-   [<span data-ttu-id="9cd17-116">Seguridad con el adaptador de Siebel y BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9cd17-116">Security with Siebel adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)
  
-   [<span data-ttu-id="9cd17-117">Programación segura con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="9cd17-117">Secure programming with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)
  
-   [<span data-ttu-id="9cd17-118">Procedimientos recomendados para proteger el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="9cd17-118">Best practices to secure the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)