---
title: Informe de estado del contenido de mensaje EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29acab25-354d-42f0-b6e3-37ebca47addb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62dbb260bb23e3ed5de7e8d416158a0e142c6c32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238868"
---
# <a name="edi-message-content-status-report"></a><span data-ttu-id="d2d05-102">Informe de estado del contenido del mensaje EDI</span><span class="sxs-lookup"><span data-stu-id="d2d05-102">EDI Message Content Status Report</span></span>

## <a name="overview"></a><span data-ttu-id="d2d05-103">Información general</span><span class="sxs-lookup"><span data-stu-id="d2d05-103">Overview</span></span>
<span data-ttu-id="d2d05-104">Este informe de estado muestra los encabezados y la carga de un conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="d2d05-104">This status report displays the headers and payload of a transaction set.</span></span> <span data-ttu-id="d2d05-105">Mostrar este informe haciendo clic en un conjunto de transacciones en el informe de estado de detalles del conjunto de transacciones y, a continuación, haga clic en **contenido de conjunto de transacciones de vista**.</span><span class="sxs-lookup"><span data-stu-id="d2d05-105">You display this report by right-clicking a transaction set within the Transaction Set Details status report, and then clicking **View Transaction Set Content**.</span></span>  
  
 <span data-ttu-id="d2d05-106">Este informe solo está disponible si ha seleccionado la **almacenar carga y conjunto de transacciones para los informes** propiedad en la página General del cuadro de diálogo Propiedades de EDI de la entidad relacionada.</span><span class="sxs-lookup"><span data-stu-id="d2d05-106">This report is available only if you have selected the **Store transaction set/payload for reporting** property in the General Page of the EDI Properties dialog box for the related party.</span></span>  
  
 <span data-ttu-id="d2d05-107">Este informe proporciona dos vistas de contenido:</span><span class="sxs-lookup"><span data-stu-id="d2d05-107">This report provides two views of the content:</span></span>  
  
-   <span data-ttu-id="d2d05-108">Una vista de Formato de texto, que muestra el contenido del conjunto de transacciones de forma legible, como en un archivo de texto EDI.</span><span class="sxs-lookup"><span data-stu-id="d2d05-108">A Text Format view that shows the contents of the transaction set in human-readable form, as in an EDI text file.</span></span> <span data-ttu-id="d2d05-109">Esta vista muestra el encabezado ST, la carga del conjunto de transacciones y el finalizador SE, con un segmento por línea.</span><span class="sxs-lookup"><span data-stu-id="d2d05-109">This view shows the ST header, the transaction set payload, and the SE trailer, with each segment on a separate line.</span></span>  
  
-   <span data-ttu-id="d2d05-110">Una vista de Formato binario, que muestra el contenido del conjunto de transacciones en un formato de texto no delimitado y una tabla de representaciones hexadecimales para cada carácter ASCII del conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="d2d05-110">A Binary Format view that shows the contents of the transaction set in non-delimited text format and a table of the hexadecimal representations for each ASCII character in the transaction set.</span></span>  
  
