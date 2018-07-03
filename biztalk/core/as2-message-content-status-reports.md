---
title: AS2 Informes de estado del contenido del mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6244aa59-a80d-450b-ab95-9a5e14c0c40e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f8461e2433f9d7cfb14dd0d4961704ec624db8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996893"
---
# <a name="as2-message-content-status-reports"></a><span data-ttu-id="d8b9d-102">Informes de estado del contenido del mensaje AS2</span><span class="sxs-lookup"><span data-stu-id="d8b9d-102">AS2 Message Content Status Reports</span></span>

## <a name="overview"></a><span data-ttu-id="d8b9d-103">Información general</span><span class="sxs-lookup"><span data-stu-id="d8b9d-103">Overview</span></span>
<span data-ttu-id="d8b9d-104">En estos informes de estado se muestran las propiedades de contexto, los encabezados y la carga de un mensaje AS2 o un MDN.</span><span class="sxs-lookup"><span data-stu-id="d8b9d-104">These status reports display the context properties, headers and payload of an AS2 message or an MDN.</span></span> <span data-ttu-id="d8b9d-105">Hay tres informes de estado del contenido del mensaje AS2:</span><span class="sxs-lookup"><span data-stu-id="d8b9d-105">There are three AS2 message content status reports:</span></span>  
  
- <span data-ttu-id="d8b9d-106">Informe de formato de mensaje</span><span class="sxs-lookup"><span data-stu-id="d8b9d-106">Message Wire Format report</span></span>  
  
- <span data-ttu-id="d8b9d-107">Informe de formato con descodificación de mensaje</span><span class="sxs-lookup"><span data-stu-id="d8b9d-107">Message Decoded Format report</span></span>  
  
- <span data-ttu-id="d8b9d-108">Informe de mensaje MDN</span><span class="sxs-lookup"><span data-stu-id="d8b9d-108">Mdn Message report</span></span>  
  
  <span data-ttu-id="d8b9d-109">Para ver uno de estos informes haciendo clic en un mensaje AS2 en el informe de estado AS2/MDN y, a continuación, haga clic en **ver formato del mensaje**, **ver formato descodificado del mensaje**, o **vista Mdn Mensaje**.</span><span class="sxs-lookup"><span data-stu-id="d8b9d-109">You display one of these reports by right-clicking an AS2 message within the AS2/MDN status report, and then clicking **View Message Wire Format**, **View Message Decoded Format**, or **View Mdn Message**.</span></span> <span data-ttu-id="d8b9d-110">El comando de MDN mostrará el MDN que se correlaciona con el mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="d8b9d-110">The MDN command will display the MDN that is correlated to the AS2 message.</span></span>  
  
  <span data-ttu-id="d8b9d-111">Todos estos informes se encuentran disponibles solo si ha seleccionado las propiedades "Almacenar mensajes en la base de datos sin repudio" correspondientes de la página Entidad como remitente del mensaje AS2 o la página Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2 de la entidad relacionada.</span><span class="sxs-lookup"><span data-stu-id="d8b9d-111">Each of these reports is available only if you have selected the corresponding "Store messages in non-repudiation database" properties in the Party as AS2 Message Sender page or Party as AS2 Message Receiver page of the AS2 Properties dialog box for the related party.</span></span> <span data-ttu-id="d8b9d-112">Los comandos almacenan mensajes AS2 o MDN en el formato correspondiente o con formato descodificado en la base de datos de BizTalkDTADb.</span><span class="sxs-lookup"><span data-stu-id="d8b9d-112">The commands store AS2 messages or MDNs in wire format or decoded format in the BizTalkDTADb database.</span></span>  
  
  <span data-ttu-id="d8b9d-113">Este informe usa la **cuadro de diálogo de propiedades de mensaje detalles** (consulte los detalles de la interfaz de usuario [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) para mostrar los datos de mensaje, con la información dividida en páginas:</span><span class="sxs-lookup"><span data-stu-id="d8b9d-113">This report uses the **Message Details Properties Dialog Box** (see the UI details [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) to display message data, with information separated into pages:</span></span>  
  
|<span data-ttu-id="d8b9d-114">Página</span><span class="sxs-lookup"><span data-stu-id="d8b9d-114">Page</span></span>|<span data-ttu-id="d8b9d-115">Datos mostrados</span><span class="sxs-lookup"><span data-stu-id="d8b9d-115">Data Displayed</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="d8b9d-116">**General**</span><span class="sxs-lookup"><span data-stu-id="d8b9d-116">**General**</span></span>|<span data-ttu-id="d8b9d-117">Información general acerca del mensaje</span><span class="sxs-lookup"><span data-stu-id="d8b9d-117">Overview information about the message</span></span>|  
|<span data-ttu-id="d8b9d-118">**Contexto**</span><span class="sxs-lookup"><span data-stu-id="d8b9d-118">**Context**</span></span>|<span data-ttu-id="d8b9d-119">Propiedades de contexto asociadas con este mensaje</span><span class="sxs-lookup"><span data-stu-id="d8b9d-119">Context properties associated with this message</span></span>|  
|<span data-ttu-id="d8b9d-120">**Partes del mensaje**</span><span class="sxs-lookup"><span data-stu-id="d8b9d-120">**Message Parts**</span></span>|<span data-ttu-id="d8b9d-121">Carga de documentos individuales dentro de este mensaje.</span><span class="sxs-lookup"><span data-stu-id="d8b9d-121">Individual document payload contained within this message.</span></span> <span data-ttu-id="d8b9d-122">Cada documento se puede ver como texto o binario:</span><span class="sxs-lookup"><span data-stu-id="d8b9d-122">Each document can be viewed as either text or binary:</span></span><br /><br /> <span data-ttu-id="d8b9d-123">-Vista de formato de texto muestra el contenido del mensaje AS2 o MDN en forma legible, como en un archivo de texto EDI.</span><span class="sxs-lookup"><span data-stu-id="d8b9d-123">-   Text Format view shows the contents of the AS2 message or MDN in human-readable form, as in an EDI text file.</span></span> <span data-ttu-id="d8b9d-124">Esta vista muestra los encabezados AS2, finalizadores EDI y la carga EDI, con cada uno de los segmentos en una línea individual.</span><span class="sxs-lookup"><span data-stu-id="d8b9d-124">This view shows the AS2 headers, EDI trailers, and EDI payload, with each segment on a separate line.</span></span><br /><span data-ttu-id="d8b9d-125">-La vista formato binario muestra el contenido del mensaje AS2 o MDN en formato de texto no delimitado y una tabla de representaciones hexadecimales para cada carácter ASCII en el mensaje AS2 o MDN.</span><span class="sxs-lookup"><span data-stu-id="d8b9d-125">-   Binary Format view shows the contents of the AS2 message or MDN in non-delimited text format and a table of the hexadecimal representations for each ASCII character in the AS2 message or MDN.</span></span>|