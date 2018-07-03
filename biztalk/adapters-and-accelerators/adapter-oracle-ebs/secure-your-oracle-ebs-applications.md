---
title: Proteger las aplicaciones de Oracle EBS | Microsoft Docs
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
ms.openlocfilehash: 03bf79d6a1324658101c2f12de758848ce7794fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996949"
---
# <a name="secure-your-oracle-ebs-applications"></a><span data-ttu-id="d7c69-102">Proteger las aplicaciones de Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="d7c69-102">Secure your Oracle EBS applications</span></span>
<span data-ttu-id="d7c69-103">Las aplicaciones de Oracle E-Business tratan con la información empresarial confidencial, como los detalles de la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="d7c69-103">Oracle E-Business applications deal with sensitive business information such as customer account details.</span></span> <span data-ttu-id="d7c69-104">Las aplicaciones que usan el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida podría accidentalmente exponerla para tener acceso a los actores no autorizado, a menos que se realizan los esfuerzos para proteger y asegurar los datos durante transmisión.</span><span class="sxs-lookup"><span data-stu-id="d7c69-104">Applications that use the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="d7c69-105">Seguridad y protección de datos normalmente son pensar en los siguientes términos:</span><span class="sxs-lookup"><span data-stu-id="d7c69-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="d7c69-106">*Autorización* controla el acceso a un recurso basado en la identidad del solicitante.</span><span class="sxs-lookup"><span data-stu-id="d7c69-106">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
- <span data-ttu-id="d7c69-107">*Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.</span><span class="sxs-lookup"><span data-stu-id="d7c69-107">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
- <span data-ttu-id="d7c69-108">*Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.</span><span class="sxs-lookup"><span data-stu-id="d7c69-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="d7c69-109">*Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, para que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.</span><span class="sxs-lookup"><span data-stu-id="d7c69-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="d7c69-110">Otra área importante de preocupación es las credenciales de contraseña de nombre de usuario que proporcione a los [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7c69-110">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="d7c69-111">El adaptador usa estas credenciales para abrir las conexiones a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="d7c69-111">The adapter uses these credentials to open connections to the Oracle database.</span></span> <span data-ttu-id="d7c69-112">Estas credenciales se pueden proporcionar en la conexión URI; Sin embargo, dado que el nombre de usuario y la contraseña son texto no cifrado, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] proporciona los métodos alternativos que puede usar para proporcionar estas credenciales en forma más segura.</span><span class="sxs-lookup"><span data-stu-id="d7c69-112">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
  <span data-ttu-id="d7c69-113">Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que se desarrollan con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7c69-113">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
