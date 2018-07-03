---
title: Proteger las aplicaciones de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eabb9c260ed835a7c4cac3183000327767bb9cd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014517"
---
# <a name="secure-your-sql-applications"></a><span data-ttu-id="38f4d-102">Proteger las aplicaciones de SQL</span><span class="sxs-lookup"><span data-stu-id="38f4d-102">Secure your SQL applications</span></span>
## <a name="overview"></a><span data-ttu-id="38f4d-103">Información general</span><span class="sxs-lookup"><span data-stu-id="38f4d-103">Overview</span></span>
<span data-ttu-id="38f4d-104">Las bases de datos de SQL Server suelen contengan información empresarial confidencial, como los detalles de la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="38f4d-104">SQL Server databases often contain sensitive business information such as customer account details.</span></span> <span data-ttu-id="38f4d-105">Las aplicaciones que usan el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida podría accidentalmente exponerla para tener acceso a los actores no autorizado, a menos que se realizan los esfuerzos para proteger y asegurar los datos durante transmisión.</span><span class="sxs-lookup"><span data-stu-id="38f4d-105">Applications that use the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="38f4d-106">Seguridad y protección de datos normalmente son pensar en los siguientes términos:</span><span class="sxs-lookup"><span data-stu-id="38f4d-106">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="38f4d-107">*Autorización* controla el acceso a un recurso basado en la identidad del solicitante.</span><span class="sxs-lookup"><span data-stu-id="38f4d-107">*Authorization* controls access to a resource based on the identity of the requestor.</span></span>  
  
- <span data-ttu-id="38f4d-108">*Autenticación* proporciona mecanismos para comprobar la identidad del solicitante.</span><span class="sxs-lookup"><span data-stu-id="38f4d-108">*Authentication* provides mechanisms for verifying the identity of a requestor.</span></span>  
  
- <span data-ttu-id="38f4d-109">*Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.</span><span class="sxs-lookup"><span data-stu-id="38f4d-109">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="38f4d-110">*Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, para que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.</span><span class="sxs-lookup"><span data-stu-id="38f4d-110">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="38f4d-111">Otra área importante de preocupación es las credenciales de contraseña de nombre de usuario que proporcione a los [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38f4d-111">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="38f4d-112">El adaptador usa estas credenciales para abrir conexiones con el sistema SQL.</span><span class="sxs-lookup"><span data-stu-id="38f4d-112">The adapter uses these credentials to open connections to the SQL system.</span></span> <span data-ttu-id="38f4d-113">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no admite las credenciales que proporcionarse en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="38f4d-113">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not allow credentials to be supplied in the connection URI.</span></span> <span data-ttu-id="38f4d-114">Esto impide que las credenciales de introducción expuesto accidentalmente.</span><span class="sxs-lookup"><span data-stu-id="38f4d-114">This prevents the credentials from getting exposed inadvertently.</span></span> <span data-ttu-id="38f4d-115">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] proporciona dos métodos alternativos para proporcionar estas credenciales en un modo más seguro:</span><span class="sxs-lookup"><span data-stu-id="38f4d-115">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] provides two alternative methods to supply these credentials in a more secure manner:</span></span>  
  
  <span data-ttu-id="38f4d-116">Seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="38f4d-116">Integrated Security.</span></span> <span data-ttu-id="38f4d-117">En este caso, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] usa Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] credenciales.</span><span class="sxs-lookup"><span data-stu-id="38f4d-117">In this case, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] credentials.</span></span> <span data-ttu-id="38f4d-118">Debe configurar el servidor de SQL server para que acepte estas credenciales para que funcione este método.</span><span class="sxs-lookup"><span data-stu-id="38f4d-118">You must configure the SQL server to accept these credentials for this method to work.</span></span>  
  
  <span data-ttu-id="38f4d-119">Enterprise Single Sign-on (SSO).</span><span class="sxs-lookup"><span data-stu-id="38f4d-119">Enterprise Single Sign-on (SSO).</span></span> <span data-ttu-id="38f4d-120">Para obtener más información sobre el uso de SSO, vea [seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) .</span><span class="sxs-lookup"><span data-stu-id="38f4d-120">For more information about using SSO, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) .</span></span>  
  
  <span data-ttu-id="38f4d-121">Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que se desarrollan con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38f4d-121">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38f4d-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="38f4d-122">In This Section</span></span>  
  
-   [<span data-ttu-id="38f4d-123">Seguridad entre el servidor SQL Server y el adaptador</span><span class="sxs-lookup"><span data-stu-id="38f4d-123">Security between the SQL Server and the adapter</span></span>](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [<span data-ttu-id="38f4d-124">Seguridad con el adaptador de SQL y BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="38f4d-124">Security with the SQL adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [<span data-ttu-id="38f4d-125">Programación segura con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="38f4d-125">Secure programming with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [<span data-ttu-id="38f4d-126">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="38f4d-126">Best practices</span></span>](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)