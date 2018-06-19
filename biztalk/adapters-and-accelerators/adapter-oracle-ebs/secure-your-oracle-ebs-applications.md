---
title: Proteger las aplicaciones de Oracle EBS | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76147120-57a8-4959-a0ff-77d04dee06a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9a7427d36ead6ba91e0d68b1080c9ab4f5155fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215004"
---
# <a name="secure-your-oracle-ebs-applications"></a><span data-ttu-id="548ec-102">Proteger las aplicaciones de Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="548ec-102">Secure your Oracle EBS applications</span></span>
<span data-ttu-id="548ec-103">Las aplicaciones de Oracle E-Business ocupan de la información empresarial confidencial, como los detalles de cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="548ec-103">Oracle E-Business applications deal with sensitive business information such as customer account details.</span></span> <span data-ttu-id="548ec-104">Las aplicaciones que utilizan el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida puede accidentalmente exponerla obtener acceso a los actores no autorizados, a menos que se haga un esfuerzo para proteger y proteger los datos durante la transmisión.</span><span class="sxs-lookup"><span data-stu-id="548ec-104">Applications that use the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="548ec-105">Seguridad y protección de datos normalmente se considera de en los siguientes términos:</span><span class="sxs-lookup"><span data-stu-id="548ec-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
-   <span data-ttu-id="548ec-106">*Autorización* controla el acceso a un recurso basado en la identidad del solicitante.</span><span class="sxs-lookup"><span data-stu-id="548ec-106">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
-   <span data-ttu-id="548ec-107">*Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.</span><span class="sxs-lookup"><span data-stu-id="548ec-107">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
-   <span data-ttu-id="548ec-108">*Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.</span><span class="sxs-lookup"><span data-stu-id="548ec-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
-   <span data-ttu-id="548ec-109">*Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, por lo que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.</span><span class="sxs-lookup"><span data-stu-id="548ec-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
 <span data-ttu-id="548ec-110">Otra área importante del problema es las credenciales de contraseña de nombre de usuario que proporcione al [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="548ec-110">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="548ec-111">El adaptador utiliza estas credenciales para abrir las conexiones a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="548ec-111">The adapter uses these credentials to open connections to the Oracle database.</span></span> <span data-ttu-id="548ec-112">Estas credenciales se pueden proporcionar en la conexión URI; Sin embargo, dado que el nombre de usuario y la contraseña son texto no cifrado, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] proporciona métodos que puede usar para proporcionar estas credenciales de forma más segura.</span><span class="sxs-lookup"><span data-stu-id="548ec-112">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
 <span data-ttu-id="548ec-113">Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que desarrolle con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="548ec-113">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
