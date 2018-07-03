---
title: 'De sesión único: Evento 10526 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f72d466-8b63-453c-b608-f9d64f635f65
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 433190146391c494ff3b890c8332cc15fb947753
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024458"
---
# <a name="single-sign-on-event-10526"></a><span data-ttu-id="67591-102">De sesión único: Evento 10526</span><span class="sxs-lookup"><span data-stu-id="67591-102">Single Sign-On: Event 10526</span></span>
## <a name="details"></a><span data-ttu-id="67591-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="67591-103">Details</span></span>  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="67591-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="67591-104">Product Name</span></span>   |                                                                     <span data-ttu-id="67591-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="67591-105">Enterprise Single Sign-On</span></span>                                                                     |
| <span data-ttu-id="67591-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="67591-106">Product Version</span></span> |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="67591-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="67591-107">Event ID</span></span>     |                                                                               <span data-ttu-id="67591-108">10526</span><span class="sxs-lookup"><span data-stu-id="67591-108">10526</span></span>                                                                               |
|  <span data-ttu-id="67591-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="67591-109">Event Source</span></span>   |                                                                              <span data-ttu-id="67591-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="67591-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="67591-111">Componente</span><span class="sxs-lookup"><span data-stu-id="67591-111">Component</span></span>    |                                                                                <span data-ttu-id="67591-112">N\D</span><span class="sxs-lookup"><span data-stu-id="67591-112">N\A</span></span>                                                                                |
|  <span data-ttu-id="67591-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="67591-113">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="67591-114">SSO_ERROR_GENERATE_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="67591-114">SSO_ERROR_GENERATE_SECRET_FAILED</span></span>                                                                  |
|  <span data-ttu-id="67591-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="67591-115">Message Text</span></span>   | <span data-ttu-id="67591-116">No se pudo generar un secreto principal nuevo.%r</span><span class="sxs-lookup"><span data-stu-id="67591-116">Failed to generate a new master secret.%r</span></span><br /><br /> <span data-ttu-id="67591-117">Usuario cliente: %1 %r</span><span class="sxs-lookup"><span data-stu-id="67591-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="67591-118">Equipo cliente: %2%r</span><span class="sxs-lookup"><span data-stu-id="67591-118">Client Computer:%2%r</span></span><br /><br /> <span data-ttu-id="67591-119">Id. de seguimiento: %3 %r</span><span class="sxs-lookup"><span data-stu-id="67591-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="67591-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="67591-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="67591-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="67591-121">Explanation</span></span>  
 <span data-ttu-id="67591-122">Este evento de error indica que no se puedo llevar a cabo el intento de generar un secreto principal nuevo por parte del usuario.</span><span class="sxs-lookup"><span data-stu-id="67591-122">This Error event indicates that a user attempt to generate a new master secret has failed.</span></span> <span data-ttu-id="67591-123">Esto puede deberse a problemas de permisos (se debe ser un administrador de SSO para generar el secreto principal) o a problemas durante la escritura del secreto principal en el archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="67591-123">This might be due to permissions issues (you must be an SSO Administrator to generate the master secret) or possibly there were problems writing the master secret to the backup file.</span></span> <span data-ttu-id="67591-124">En estos casos, debería haber mensajes relacionados en el registro de eventos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67591-124">In these cases there should be related messages in the Application event log.</span></span>  

## <a name="user-action"></a><span data-ttu-id="67591-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="67591-125">User Action</span></span>  
 <span data-ttu-id="67591-126">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="67591-126">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="67591-127">Compruebe si el registro de eventos de la aplicación contiene eventos o errores asociados.</span><span class="sxs-lookup"><span data-stu-id="67591-127">Check the Application event log for associated events or errors.</span></span>  

- <span data-ttu-id="67591-128">Compruebe si dispone de los permisos de administrador de SSO correspondientes.</span><span class="sxs-lookup"><span data-stu-id="67591-128">Check that you have the appropriate SSO Administrator permissions.</span></span>  

  <span data-ttu-id="67591-129">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="67591-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="67591-130">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="67591-130">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="67591-131">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="67591-131">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
