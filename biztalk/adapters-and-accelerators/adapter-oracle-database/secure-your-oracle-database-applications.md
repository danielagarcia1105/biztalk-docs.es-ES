---
title: Proteger las aplicaciones de base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, security
- authorization
- data protection
- adapter, data protection
- authentication
- security
ms.assetid: c5f18b0a-1c8e-44c6-ba7e-470fa186f636
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8601463c02e32221c369023f05ed2fd3731bb4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214708"
---
# <a name="secure-your-oracle-database-applications"></a><span data-ttu-id="3de24-102">Proteger las aplicaciones de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="3de24-102">Secure your Oracle Database applications</span></span>
## <a name="data-protection-and-security-overview"></a><span data-ttu-id="3de24-103">Información general de seguridad y protección de datos</span><span class="sxs-lookup"><span data-stu-id="3de24-103">Data protection and security overview</span></span>
<span data-ttu-id="3de24-104">A menudo, una base de datos contiene la información empresarial confidencial, como los detalles de cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="3de24-104">A database often contains sensitive business information such as customer account details.</span></span> <span data-ttu-id="3de24-105">Las aplicaciones que utilizan el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida puede accidentalmente exponerla obtener acceso a los actores no autorizados, a menos que se haga un esfuerzo para proteger y proteger los datos durante la transmisión.</span><span class="sxs-lookup"><span data-stu-id="3de24-105">Applications that use the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="3de24-106">Seguridad y protección de datos normalmente se considera de en los siguientes términos:</span><span class="sxs-lookup"><span data-stu-id="3de24-106">Data protection and security are usually thought of in the following terms:</span></span>  
  
-   <span data-ttu-id="3de24-107">*Autorización* controla el acceso a un recurso basado en la identidad del solicitante.</span><span class="sxs-lookup"><span data-stu-id="3de24-107">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
-   <span data-ttu-id="3de24-108">*Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.</span><span class="sxs-lookup"><span data-stu-id="3de24-108">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
-   <span data-ttu-id="3de24-109">*Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.</span><span class="sxs-lookup"><span data-stu-id="3de24-109">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
-   <span data-ttu-id="3de24-110">*Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, por lo que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.</span><span class="sxs-lookup"><span data-stu-id="3de24-110">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
 <span data-ttu-id="3de24-111">Otra área importante del problema es las credenciales de contraseña de nombre de usuario que proporcione al [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de24-111">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="3de24-112">El adaptador utiliza estas credenciales para abrir las conexiones a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="3de24-112">The adapter uses these credentials to open connections to the Oracle database.</span></span> <span data-ttu-id="3de24-113">Estas credenciales se pueden proporcionar en la conexión URI; Sin embargo, dado que el nombre de usuario y la contraseña son texto no cifrado, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] proporciona métodos que puede usar para proporcionar estas credenciales de forma más segura.</span><span class="sxs-lookup"><span data-stu-id="3de24-113">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
 <span data-ttu-id="3de24-114">Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que desarrolle con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3de24-114">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3de24-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3de24-115">In this section</span></span>  
  
-   [<span data-ttu-id="3de24-116">Seguridad entre la base de datos de Oracle y el adaptador</span><span class="sxs-lookup"><span data-stu-id="3de24-116">Security between the Oracle Database and the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)
  
-   [<span data-ttu-id="3de24-117">Seguridad con el adaptador de la base de datos de Oracle y el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3de24-117">Security with the Oracle Database adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)  
  
-   [<span data-ttu-id="3de24-118">Programación segura con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="3de24-118">Secure programming with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md) 
  
-   [<span data-ttu-id="3de24-119">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="3de24-119">Best practices</span></span>](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)