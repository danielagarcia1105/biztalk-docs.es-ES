---
title: Enviar informe de detalles de estado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3cbc9d44-9a9a-4272-a138-ebd126a9f809
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2335b10da205258f32a6676a6fee2a3ff32fef65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268420"
---
# <a name="resend-status-details-report"></a><span data-ttu-id="01e52-102">Reenvío del informe de detalles de estado</span><span class="sxs-lookup"><span data-stu-id="01e52-102">Resend Status Details Report</span></span>
<span data-ttu-id="01e52-103">En este informe de estado se muestra información sobre el número de reintentos efectuados cuando las propiedades de entidad y de receptor AS2 de una entidad se han configurado para reenviar el mensaje AS2 si no se ha recibido un MDN.</span><span class="sxs-lookup"><span data-stu-id="01e52-103">This status report displays information on retry attempts made when the Party as AS2 Receiver properties of a party are configured to resend the AS2 message if an MDN is not received.</span></span>  
  
 <span data-ttu-id="01e52-104">Para mostrar este informe haciendo doble clic en un mensaje en el informe de estado AS2/MDN y, a continuación, haga clic en **ver estado de mensajería confiable**.</span><span class="sxs-lookup"><span data-stu-id="01e52-104">You display this report by right-clicking on a message in the AS2/MDN status report, and then clicking **View Reliable Messaging Status**.</span></span> <span data-ttu-id="01e52-105">En la página de reenvío de detalles de estado se mostrará información sobre los intentos de reenvío efectuados para ese mensaje.</span><span class="sxs-lookup"><span data-stu-id="01e52-105">The Resend Status Details page will then display information on the resend attempts made for this message.</span></span>  
  
 <span data-ttu-id="01e52-106">Este informe solo está disponible si ha seleccionado **reenviar mensaje AS2 si no se recibe MDN** en la entidad como propiedades de receptor del mensaje AS2 de la entidad relacionada.</span><span class="sxs-lookup"><span data-stu-id="01e52-106">This report is only available if you have selected **Resend AS2 message if MDN not received** in the Party as AS2 Message Receiver properties for the related party.</span></span>  
  
 <span data-ttu-id="01e52-107">En el informe se muestra información sobre los reintentos efectuados para el mensaje en las páginas siguientes:</span><span class="sxs-lookup"><span data-stu-id="01e52-107">The report displays information on the retry attempts made for the message on the following pages:</span></span>  
  
|<span data-ttu-id="01e52-108">Página</span><span class="sxs-lookup"><span data-stu-id="01e52-108">Page</span></span>|<span data-ttu-id="01e52-109">Datos mostrados</span><span class="sxs-lookup"><span data-stu-id="01e52-109">Data Displayed</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="01e52-110">**General**</span><span class="sxs-lookup"><span data-stu-id="01e52-110">**General**</span></span>|<span data-ttu-id="01e52-111">El índice del intento de envío actual, así como la configuración de reenvío.</span><span class="sxs-lookup"><span data-stu-id="01e52-111">The index of the current send attempt as well as the resend configuration.</span></span>|  
|<span data-ttu-id="01e52-112">**Historial de reenvío**</span><span class="sxs-lookup"><span data-stu-id="01e52-112">**Resend History**</span></span>|<span data-ttu-id="01e52-113">Historial de los intentos de envío del mensaje.</span><span class="sxs-lookup"><span data-stu-id="01e52-113">A history of send attempts for the message.</span></span>|