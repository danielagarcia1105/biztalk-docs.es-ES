---
title: ProActivity en BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b924ddae-0e7f-4058-b308-7ea9537fb45f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4508507c0cf84141bc63df7a53eeab7c38c9f390
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302108"
---
# <a name="proactivity-in-biztalk-server"></a><span data-ttu-id="ee63b-102">Proactividad en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ee63b-102">Proactivity in BizTalk Server</span></span>
<span data-ttu-id="ee63b-103">Artículo técnico de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ee63b-103">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="ee63b-104">**Proactividad en BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="ee63b-104">**Proactivity in BizTalk Server**</span></span>  
  
 <span data-ttu-id="ee63b-105">**Escritor:** Tord contentos Nordahl (Bouvet AS)</span><span class="sxs-lookup"><span data-stu-id="ee63b-105">**Writer:** Tord Glad Nordahl (Bouvet AS)</span></span>  
  
 <span data-ttu-id="ee63b-106">**Revisores técnicos:** Sandro Pereira (Devscope), Jan Steef Wiggers (Motion10), Erik Thue (Bouvet AS), Alexander Thue (Bouvet AS), Saravana Kumar (BizTalk360), Mandi Ohlinger (Microsoft)</span><span class="sxs-lookup"><span data-stu-id="ee63b-106">**Technical Reviewers:** Sandro Pereira (Devscope), Steef-Jan Wiggers (Motion10), Erik Thue (Bouvet AS), Alexander Thue (Bouvet AS), Saravana Kumar  (BizTalk360), Mandi Ohlinger (Microsoft)</span></span>  
  
 <span data-ttu-id="ee63b-107">**Fecha de publicación:** julio de 2013</span><span class="sxs-lookup"><span data-stu-id="ee63b-107">**Published:** July 2013</span></span>  
  
 <span data-ttu-id="ee63b-108">**Se aplica a:** servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ee63b-108">**Applies To:** BizTalk Server</span></span>  
  
 <span data-ttu-id="ee63b-109">**Resumen:** las notas del producto se aplica desde BizTalk Server 2004 a BizTalk Server 2013 entornos.</span><span class="sxs-lookup"><span data-stu-id="ee63b-109">**Summary:** The white paper applies from BizTalk Server 2004 to BizTalk Server 2013 environments.</span></span>  <span data-ttu-id="ee63b-110">El objetivo es proporcionar más información sobre cómo ser proactivo y resolver o evitar problemas potenciales antes de que ocurran.</span><span class="sxs-lookup"><span data-stu-id="ee63b-110">The goal is to provide some insight of how to be proactive and resolve, or avoid, potential problems before they occur.</span></span> <span data-ttu-id="ee63b-111">Se aplica a todos los tipos de usuarios de BizTalk, incluidos los arquitectos, desarrolladores y administradores.</span><span class="sxs-lookup"><span data-stu-id="ee63b-111">It applies to all types of BizTalk users, including architects, developers, and administrators.</span></span> <span data-ttu-id="ee63b-112">No todos los escenarios descritos pueden producirse en su entorno y pueden producirse algunos escenarios no mencionados en este documento.</span><span class="sxs-lookup"><span data-stu-id="ee63b-112">Not all scenarios described may occur in your environment and some scenarios not mentioned in this white paper can occur.</span></span>  
  
 <span data-ttu-id="ee63b-113">Debido a la naturaleza y la importancia de BizTalk Server, configuración y prácticas recomendadas pueden variar entorno; incluida la configuración de red, diseño de arquitectura, versiones, flujo de mensajes y recursos.</span><span class="sxs-lookup"><span data-stu-id="ee63b-113">Due to the nature and importance of BizTalk Server, settings and best practices can vary by environment; including network settings, architecture design, versions, message flow, and resources.</span></span> <span data-ttu-id="ee63b-114">Estas notas del producto se describe la configuración y valores recomendados.</span><span class="sxs-lookup"><span data-stu-id="ee63b-114">This white paper discussed the common setup and recommended values.</span></span>  
  
 <span data-ttu-id="ee63b-115">Para revisar el documento, descargue el [proactividad en BizTalk Server](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Proactivity%20in%20BizTalk%20Server.docx) documento de Word.</span><span class="sxs-lookup"><span data-stu-id="ee63b-115">To review the document, please download the [Proactivity in BizTalk Server](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Proactivity%20in%20BizTalk%20Server.docx) Word document.</span></span>