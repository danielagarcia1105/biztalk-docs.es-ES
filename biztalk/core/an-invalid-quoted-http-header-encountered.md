---
title: No es válido entre comillas encontrado un encabezado HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb530ee6-ec6a-4791-ae99-b9db426c0896
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ca0d7463f4604e8a159c12fab690e494a13fb60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971013"
---
# <a name="an-invalid-quoted-http-header-encountered"></a><span data-ttu-id="acdb6-102">Se detectó un encabezado HTTP entre comillas no válido</span><span class="sxs-lookup"><span data-stu-id="acdb6-102">An invalid quoted HTTP header encountered</span></span>
## <a name="details"></a><span data-ttu-id="acdb6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="acdb6-103">Details</span></span>  
  
|                 |                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="acdb6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="acdb6-104">Product Name</span></span>   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| <span data-ttu-id="acdb6-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="acdb6-105">Product Version</span></span> |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                          |
|    <span data-ttu-id="acdb6-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="acdb6-106">Event ID</span></span>     |                                                      -                                                       |
|  <span data-ttu-id="acdb6-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="acdb6-107">Event Source</span></span>   |            <span data-ttu-id="acdb6-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acdb6-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>            |
|    <span data-ttu-id="acdb6-109">Componente</span><span class="sxs-lookup"><span data-stu-id="acdb6-109">Component</span></span>    |                                                  <span data-ttu-id="acdb6-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="acdb6-110">AS2 Engine</span></span>                                                  |
|  <span data-ttu-id="acdb6-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="acdb6-111">Symbolic Name</span></span>  |                                                      -                                                       |
|  <span data-ttu-id="acdb6-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="acdb6-112">Message Text</span></span>   | <span data-ttu-id="acdb6-113">Se detectó un encabezado HTTP entre comillas no válido.</span><span class="sxs-lookup"><span data-stu-id="acdb6-113">An invalid quoted HTTP header encountered.</span></span>  <span data-ttu-id="acdb6-114">Los detalles son los siguientes: nombre de encabezado: "{0}" valor de encabezado: "{1}"</span><span class="sxs-lookup"><span data-stu-id="acdb6-114">Details are as follows:  Header Name: "{0}"  Header Value: "{1}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="acdb6-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="acdb6-115">Explanation</span></span>  
 <span data-ttu-id="acdb6-116">Este evento de error,  indica que la canalización de recepción AS2 o que la canalización de envío AS2 no pudo procesar el mensaje AS2 porque el nombre del encabezado HTTP AS2-From o AS2-To del mensaje no se entrecomilló correctamente.</span><span class="sxs-lookup"><span data-stu-id="acdb6-116">This Error/Warning/Information event indicates that the AS2 receive pipeline or the AS2 send pipeline could not process the AS2 message because the name of the AS2-From or AS2-To HTTP header in the message was not quoted correctly.</span></span> <span data-ttu-id="acdb6-117">El nombre del encabezado se entrecomilla con el fin de ajustar un espacio, una barra invertida o comillas dentro del nombre.</span><span class="sxs-lookup"><span data-stu-id="acdb6-117">The header name is quoted in order to accommodate a space, backslash, or double quotes within the name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="acdb6-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="acdb6-118">User Action</span></span>  
 <span data-ttu-id="acdb6-119">Para resolver este error, entrecomille el nombre del encabezado en el mensaje AS2 según las reglas que se indican en la sección 6.2, "AS2 System Identifiers", en RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2").</span><span class="sxs-lookup"><span data-stu-id="acdb6-119">To resolve this error, quote the header name in the AS2 message in accordance with the rules stated in section 6.2, "AS2 System Identifiers", in RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)".</span></span>