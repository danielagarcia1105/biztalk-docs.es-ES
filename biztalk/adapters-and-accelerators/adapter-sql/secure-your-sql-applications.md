---
title: Proteger las aplicaciones SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d631bc3ad87e9a8ec8ac51850b7dbe1eb244c140
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-sql-applications"></a><span data-ttu-id="bf33e-102">Proteger las aplicaciones de SQL</span><span class="sxs-lookup"><span data-stu-id="bf33e-102">Secure your SQL applications</span></span>
## <a name="overview"></a><span data-ttu-id="bf33e-103">Información general</span><span class="sxs-lookup"><span data-stu-id="bf33e-103">Overview</span></span>
<span data-ttu-id="bf33e-104">Las bases de datos de SQL Server suelen contengan información empresarial confidencial, como los detalles de cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="bf33e-104">SQL Server databases often contain sensitive business information such as customer account details.</span></span> <span data-ttu-id="bf33e-105">Las aplicaciones que utilizan el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida puede accidentalmente exponerla obtener acceso a los actores no autorizados, a menos que se haga un esfuerzo para proteger y proteger los datos durante la transmisión.</span><span class="sxs-lookup"><span data-stu-id="bf33e-105">Applications that use the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="bf33e-106">Seguridad y protección de datos normalmente se considera de en los siguientes términos:</span><span class="sxs-lookup"><span data-stu-id="bf33e-106">Data protection and security are usually thought of in the following terms:</span></span>  
  
-   <span data-ttu-id="bf33e-107">*Autorización* controla el acceso a un recurso basado en la identidad del solicitante.</span><span class="sxs-lookup"><span data-stu-id="bf33e-107">*Authorization* controls access to a resource based on the identity of the requestor.</span></span>  
  
-   <span data-ttu-id="bf33e-108">*Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.</span><span class="sxs-lookup"><span data-stu-id="bf33e-108">*Authentication* provides mechanisms for verifying the identity of a requestor.</span></span>  
  
-   <span data-ttu-id="bf33e-109">*Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.</span><span class="sxs-lookup"><span data-stu-id="bf33e-109">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
-   <span data-ttu-id="bf33e-110">*Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, por lo que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.</span><span class="sxs-lookup"><span data-stu-id="bf33e-110">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
 <span data-ttu-id="bf33e-111">Otra área importante del problema es las credenciales de contraseña de nombre de usuario que proporcione al [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf33e-111">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="bf33e-112">El adaptador utiliza estas credenciales para abrir conexiones con el sistema SQL.</span><span class="sxs-lookup"><span data-stu-id="bf33e-112">The adapter uses these credentials to open connections to the SQL system.</span></span> <span data-ttu-id="bf33e-113">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no permitir credenciales debe proporcionarse en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="bf33e-113">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not allow credentials to be supplied in the connection URI.</span></span> <span data-ttu-id="bf33e-114">Esto impide que las credenciales obtener expone accidentalmente.</span><span class="sxs-lookup"><span data-stu-id="bf33e-114">This prevents the credentials from getting exposed inadvertently.</span></span> <span data-ttu-id="bf33e-115">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] proporciona dos métodos alternativos para proporcionar estas credenciales de un modo más seguro:</span><span class="sxs-lookup"><span data-stu-id="bf33e-115">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] provides two alternative methods to supply these credentials in a more secure manner:</span></span>  
  
 <span data-ttu-id="bf33e-116">Seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="bf33e-116">Integrated Security.</span></span> <span data-ttu-id="bf33e-117">En este caso, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] utiliza Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] credenciales.</span><span class="sxs-lookup"><span data-stu-id="bf33e-117">In this case, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] credentials.</span></span> <span data-ttu-id="bf33e-118">Debe configurar el servidor de SQL server para que acepte estas credenciales para que funcione este método.</span><span class="sxs-lookup"><span data-stu-id="bf33e-118">You must configure the SQL server to accept these credentials for this method to work.</span></span>  
  
 <span data-ttu-id="bf33e-119">Enterprise Single Sign-on (SSO).</span><span class="sxs-lookup"><span data-stu-id="bf33e-119">Enterprise Single Sign-on (SSO).</span></span> <span data-ttu-id="bf33e-120">Para obtener más información acerca del uso de SSO, vea [seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) .</span><span class="sxs-lookup"><span data-stu-id="bf33e-120">For more information about using SSO, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) .</span></span>  
  
 <span data-ttu-id="bf33e-121">Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que desarrolle con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf33e-121">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bf33e-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bf33e-122">In This Section</span></span>  
  
-   [<span data-ttu-id="bf33e-123">Seguridad entre el servidor SQL Server y el adaptador</span><span class="sxs-lookup"><span data-stu-id="bf33e-123">Security between the SQL Server and the adapter</span></span>](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [<span data-ttu-id="bf33e-124">Seguridad con el adaptador de SQL y BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bf33e-124">Security with the SQL adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [<span data-ttu-id="bf33e-125">Programación segura con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="bf33e-125">Secure programming with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [<span data-ttu-id="bf33e-126">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="bf33e-126">Best practices</span></span>](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)