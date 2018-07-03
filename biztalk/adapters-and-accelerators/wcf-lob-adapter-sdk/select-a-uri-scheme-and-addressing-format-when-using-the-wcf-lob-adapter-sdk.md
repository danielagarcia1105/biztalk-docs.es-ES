---
title: Seleccione un esquema de URI y el formato de direcciones cuando se usa el SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb4feee-3d39-43ca-82ac-aba38c13bc69
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8a9e9ffd78e0740dd366f4f09d3a832e74cda94
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005773"
---
# <a name="select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="5fc16-102">Seleccione un esquema de URI y el formato de direcciones cuando se usa el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="5fc16-102">Select a URI scheme and addressing format when using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="5fc16-103">Un identificador uniforme de recursos (URI) identifica los recursos como un servicio Web o, en el caso de un adaptador que se desarrollan con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], el sistema para conectarse a, así como la acción a realizar.</span><span class="sxs-lookup"><span data-stu-id="5fc16-103">A Uniform Resource Identifier (URI) uniquely identifies resources like a Web service or, in the case of an adapter developed with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], the system to connect to as well as the action to perform.</span></span> <span data-ttu-id="5fc16-104">Esta sección proporciona una recomendación sobre cómo construir un URI para describir de forma exclusiva la dirección del extremo y la acción para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="5fc16-104">This section provides a recommendation on how to construct a URI to uniquely describe the endpoint address and the action for your adapter.</span></span>  
  
## <a name="anatomy-of-a-uri"></a><span data-ttu-id="5fc16-105">Anatomía de un URI</span><span class="sxs-lookup"><span data-stu-id="5fc16-105">Anatomy of a URI</span></span>  
 <span data-ttu-id="5fc16-106">Un URI consta de los tres componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="5fc16-106">A URI consists of the following three components:</span></span>  
  
- <span data-ttu-id="5fc16-107">**Nombre de esquema** es la parte responsable de la cadena de URI y es el primer nivel de la estructura de nomenclatura; algunos ejemplos son http, urn y contoso.</span><span class="sxs-lookup"><span data-stu-id="5fc16-107">**Scheme name** is the lead part of the URI string and is the first level of the naming structure; examples include http, urn, and contoso.</span></span>  
  
- <span data-ttu-id="5fc16-108">**Parte jerárquica** consta de información que es normalmente jerárquico y puede contener información de puerto, nombre de host y autoridad opcional.</span><span class="sxs-lookup"><span data-stu-id="5fc16-108">**Hierarchical part** consists of information that is usually hierarchical and can contain optional authority, hostname, and port information.</span></span> <span data-ttu-id="5fc16-109">Algunos ejemplos son el nombre de usuario y www.microsoft.com =User@microsoft.com:4099.</span><span class="sxs-lookup"><span data-stu-id="5fc16-109">Examples include www.microsoft.com and UserName=User@microsoft.com:4099.</span></span>  
  
- <span data-ttu-id="5fc16-110">**Consulta** contiene la información opcional marcados con un signo de interrogación (?) y normalmente se agrupan como pares clave/valor separados por una y comercial (&).</span><span class="sxs-lookup"><span data-stu-id="5fc16-110">**Query** contains optional information marked with a question mark (?) and typically grouped as key/value pairs separated by an ampersand (&).</span></span> <span data-ttu-id="5fc16-111">Por ejemplo, contoso://microsoft.com/functions?name=Find.</span><span class="sxs-lookup"><span data-stu-id="5fc16-111">For example, contoso://microsoft.com/functions?name=Find.</span></span>  
  
- <span data-ttu-id="5fc16-112">**Fragmento** se usa para almacenar información de identificación adicional que puedan ser necesarios para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="5fc16-112">**Fragment** is used to store extra identifying information that may be needed by the adapter.</span></span> <span data-ttu-id="5fc16-113">El fragmento se separa mediante un algoritmo hash (#); Por ejemplo, contoso://microsoft.com/functions?name=Find#public.</span><span class="sxs-lookup"><span data-stu-id="5fc16-113">The fragment is separated by a hash (#); for example, contoso://microsoft.com/functions?name=Find#public.</span></span>  
  
  <span data-ttu-id="5fc16-114">No se pueden usar todas las características proporcionadas por la sintaxis de URI.</span><span class="sxs-lookup"><span data-stu-id="5fc16-114">You might not use all of the features provided by the URI syntax.</span></span>  
  
## <a name="designing-the-uri"></a><span data-ttu-id="5fc16-115">Diseñar el URI</span><span class="sxs-lookup"><span data-stu-id="5fc16-115">Designing the URI</span></span>  
 <span data-ttu-id="5fc16-116">Como programador de adaptadores, tendrá que idear un URI adecuado para su sistema de línea de negocio de destino.</span><span class="sxs-lookup"><span data-stu-id="5fc16-116">As an adapter developer, you will have to devise an appropriate URI for your target line-of-business system.</span></span> <span data-ttu-id="5fc16-117">Al diseñar su URI, es importante para que sea único y descriptivo.</span><span class="sxs-lookup"><span data-stu-id="5fc16-117">When designing your URI, it is important to make it unique and meaningful.</span></span>  
  
 <span data-ttu-id="5fc16-118">Un URI único es aquel que no entra en conflicto con los URI existentes dentro de una organización y a través de otras empresas e Internet.</span><span class="sxs-lookup"><span data-stu-id="5fc16-118">A unique URI is one that does not conflict with existing URIs within an organization and across other businesses and the Internet.</span></span> <span data-ttu-id="5fc16-119">Por ejemplo, si elige un nombre de esquema, como "http" o "afs" que pueden ser reconocidos actualmente o ya ampliamente usado, pueden producirse problemas operativos o conexión porque se podrían enrutar las solicitudes a un sistema diferente y no a su adaptador.</span><span class="sxs-lookup"><span data-stu-id="5fc16-119">For example, choosing a scheme name like "http" or "afs" that may be currently recognized or already in wide use could cause connection or operational problems because requests might be routed to a different system and not to your adapter.</span></span>  
  
 <span data-ttu-id="5fc16-120">Otro aspecto importante del diseño URI es conseguir que sea significativo para la audiencia de desarrolladores que consumen el adaptador.</span><span class="sxs-lookup"><span data-stu-id="5fc16-120">Another important aspect of URI design is making it meaningful to the developer audience who will be consuming your adapter.</span></span> <span data-ttu-id="5fc16-121">Por ejemplo, si escribe un adaptador para el sistema de procesamiento de notificaciones de un médico, podría diseñar un esquema de URI que incluye el nombre de su compañía, el procesamiento nombre del sistema y la versión del sistema de reclamaciones de destino: northwind.contoso.cps.v1.0://.</span><span class="sxs-lookup"><span data-stu-id="5fc16-121">For example, if you are writing an adapter for a medical claims processing system, you could design a URI scheme that includes your company name, the target claims processing system name, and system version: northwind.contoso.cps.v1.0://.</span></span>  
  
## <a name="connecting-to-the-target-system"></a><span data-ttu-id="5fc16-122">Conectarse al sistema de destino</span><span class="sxs-lookup"><span data-stu-id="5fc16-122">Connecting to the Target System</span></span>  
 <span data-ttu-id="5fc16-123">Las cadenas de conexión tienen la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5fc16-123">Connection strings have the following syntax:</span></span>  
  
 <span data-ttu-id="5fc16-124">**\<esquema\>: //[userinfo "\@"]\<LOB de la cadena de conexión\>**</span><span class="sxs-lookup"><span data-stu-id="5fc16-124">**\<scheme\>://[userinfo "\@"]\<LOB Connection String\>**</span></span>  
  
 <span data-ttu-id="5fc16-125">Por ejemplo, podría conectarse al catálogo de contoso (un ejemplo aplicación de línea de negocio) del sistema de pedidos con los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5fc16-125">For example, you could connect to the contoso catalog ordering system (a sample line of business application) using the following:</span></span>  
  
 <span data-ttu-id="5fc16-126">**¿Northwind.contoso.v1.0://\<servername\>? Catálogo = Contoso & Integrated Security = True**</span><span class="sxs-lookup"><span data-stu-id="5fc16-126">**northwind.contoso.v1.0://\<servername\>?Catalog=Contoso&Integrated Security=True**</span></span>  
  
 <span data-ttu-id="5fc16-127">También puede proporcionar información de la entidad opcional en el URI incluido el nombre de usuario y contraseña y otras credenciales importantes.</span><span class="sxs-lookup"><span data-stu-id="5fc16-127">You can also provide optional authority information in the URI including user name and password and other important credentials.</span></span> <span data-ttu-id="5fc16-128">Sin embargo, esto puede suponer un riesgo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5fc16-128">However, this can present a security risk.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="5fc16-129">No pase las credenciales de usuario y otra información confidencial en el URI.</span><span class="sxs-lookup"><span data-stu-id="5fc16-129">Do not pass user credentials and other sensitive information in the URI.</span></span> <span data-ttu-id="5fc16-130">Esta información se podría interceptar y ver los usuarios no autorizados.</span><span class="sxs-lookup"><span data-stu-id="5fc16-130">This information could be intercepted and viewed by unauthorized users.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc16-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fc16-131">See Also</span></span>  
 [<span data-ttu-id="5fc16-132">Planear y diseñar un adaptador mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="5fc16-132">Plan and design an adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)