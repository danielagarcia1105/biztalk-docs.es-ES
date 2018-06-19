---
title: Publicar desde la consola de administración de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b78b1981-b227-4cf5-9435-6fc57963552a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbe03b1a8df67581ce73db31cd5ed4b80b7a109c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009101"
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a><span data-ttu-id="65018-102">Publicar desde la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="65018-102">Publishing from the BizTalk Server Administration Console</span></span>
<span data-ttu-id="65018-103">Si desea administrar el punto de conexión que se publica a través de la consola de administración de BizTalk Server en lugar del Portal de administración de ESB, puede hacerlo escribiendo un moniker de Universal Description, Discovery y Integration (UDDI) en el campo de descripción de los puntos de conexión Para publicar en UDDI.</span><span class="sxs-lookup"><span data-stu-id="65018-103">If you want to manage endpoint publishing through the BizTalk Server Administration Console instead of the ESB Management Portal, you can do so by entering a Universal Description, Discovery, and Integration (UDDI) moniker in the description field of the endpoints to publish to UDDI.</span></span> <span data-ttu-id="65018-104">El siguiente es un moniker de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="65018-104">The following is an example moniker.</span></span>  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 <span data-ttu-id="65018-105">Puede establecer las siguientes propiedades UDDI mediante el **descripción** campo en la consola de administración de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="65018-105">You can set the following UDDI properties using the **Description** field in the BizTalk Server Administration Console:</span></span>  
  
-   <span data-ttu-id="65018-106">**ModifiedBy**.</span><span class="sxs-lookup"><span data-stu-id="65018-106">**ModifiedBy**.</span></span> <span data-ttu-id="65018-107">Esta propiedad opcional contiene el nombre de cuenta del usuario que modificó el punto de conexión; Por ejemplo, MyDomainName\MyUserName.</span><span class="sxs-lookup"><span data-stu-id="65018-107">This optional property contains the account name of the user that modified the endpoint; for example, MyDomainName\MyUserName.</span></span>  
  
-   <span data-ttu-id="65018-108">**UDDIContact**.</span><span class="sxs-lookup"><span data-stu-id="65018-108">**UDDIContact**.</span></span> <span data-ttu-id="65018-109">Esta propiedad opcional es el nombre de contacto del usuario definido para el proveedor de negocio de UDDI.</span><span class="sxs-lookup"><span data-stu-id="65018-109">This optional property is the contact name of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="65018-110">**UDDIUserType**.</span><span class="sxs-lookup"><span data-stu-id="65018-110">**UDDIUserType**.</span></span> <span data-ttu-id="65018-111">Esta propiedad opcional es el tipo de usuario del usuario definido para el proveedor de negocio de UDDI.</span><span class="sxs-lookup"><span data-stu-id="65018-111">This optional property is the user type of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="65018-112">**UDDIEmail**.</span><span class="sxs-lookup"><span data-stu-id="65018-112">**UDDIEmail**.</span></span> <span data-ttu-id="65018-113">Esta propiedad opcional es la dirección de correo electrónico del usuario definido para el proveedor de negocio de UDDI.</span><span class="sxs-lookup"><span data-stu-id="65018-113">This optional property is the e-mail address of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="65018-114">**TransportType**.</span><span class="sxs-lookup"><span data-stu-id="65018-114">**TransportType**.</span></span> <span data-ttu-id="65018-115">Esta propiedad opcional es el tipo de adaptador de punto de conexión, como **archivo, MQS, WCF-WsHttp, SOAP, HTTP,** o **FTP**.</span><span class="sxs-lookup"><span data-stu-id="65018-115">This optional property is the endpoint adapter type, such as **FILE, MQS, WCF-WsHttp, SOAP, HTTP,** or **FTP**.</span></span>  
  
-   <span data-ttu-id="65018-116">**Estado**.</span><span class="sxs-lookup"><span data-stu-id="65018-116">**Status**.</span></span> <span data-ttu-id="65018-117">Esta propiedad opcional es el estado del punto de conexión, como **publicada** o **pendiente**.</span><span class="sxs-lookup"><span data-stu-id="65018-117">This optional property is the status of the endpoint, such as **Published** or **Pending**.</span></span> <span data-ttu-id="65018-118">El servicio de publicación de UDDI usa este atributo para detectar el estado del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="65018-118">The UDDI Publishing Service uses this attribute to discover the status of the endpoint.</span></span>  
  
-   <span data-ttu-id="65018-119">**BindingType**.</span><span class="sxs-lookup"><span data-stu-id="65018-119">**BindingType**.</span></span> <span data-ttu-id="65018-120">Esta propiedad opcional es el protocolo específico (tipo de dirección URL) que admite el enlace de UDDI, como **mailto, http, https, ftp, fax, teléfono,** o **otros**.</span><span class="sxs-lookup"><span data-stu-id="65018-120">This optional property is the specific protocol (URL Type) that the UDDI binding supports, such as **mailto, http, https, ftp, fax, phone,** or **other**.</span></span> <span data-ttu-id="65018-121">El servicio de publicación de UDDI usa este atributo para crear el enlace de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="65018-121">The UDDI Publishing Service uses this attribute to create the endpoint binding.</span></span>