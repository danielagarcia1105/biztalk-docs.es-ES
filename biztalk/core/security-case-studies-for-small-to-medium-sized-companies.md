---
title: Casos prácticos de seguridad para pequeñas y medianas empresas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
- security, examples
- security, architecture
- architecture, medium distributions
ms.assetid: b33e3f2a-ddc4-47a8-92d7-511ae0cc880e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9af0f013960e882ffe6b5c081ae1452df4aaecf1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269292"
---
# <a name="security-case-studies-for-small-to-medium-sized-companies"></a><span data-ttu-id="da02c-102">Casos prácticos de seguridad para pequeñas y medianas empresas</span><span class="sxs-lookup"><span data-stu-id="da02c-102">Security Case Studies for Small to Medium-Sized Companies</span></span>
<span data-ttu-id="da02c-103">La seguridad es una preocupación para cualquier organización que sólo pueda permitir que un grupo escogido de personas o aplicaciones tengan acceso a sus datos y recursos.</span><span class="sxs-lookup"><span data-stu-id="da02c-103">Security is a concern of any company that is serious about making sure that only a select group of people or applications can access its data and resources.</span></span> <span data-ttu-id="da02c-104">Las organizaciones pueden tener distintos planteamientos e implementaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="da02c-104">Companies approach and implement security in a variety of ways.</span></span>  
  
 <span data-ttu-id="da02c-105">Esta sección contiene instrucciones para implementar Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno seguro</span><span class="sxs-lookup"><span data-stu-id="da02c-105">This section provides guidelines for deploying Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a secure environment.</span></span> <span data-ttu-id="da02c-106">y contiene información para ayudarle a evaluar las posibles amenazas a las que se expone la implementación de BizTalk, una arquitectura de ejemplo para pequeñas y medianas empresas.</span><span class="sxs-lookup"><span data-stu-id="da02c-106">It provides information to help you assess the potential threats to your BizTalk Server implementation, a sample architecture for small and medium-size companies.</span></span>  
  
 <span data-ttu-id="da02c-107">Hoy en día es difícil llevar un negocio sin pensar en la seguridad.</span><span class="sxs-lookup"><span data-stu-id="da02c-107">It is difficult to run a business today without thinking about security.</span></span> <span data-ttu-id="da02c-108">Si realiza transacciones en línea, tendrá que proteger la información de las tarjetas de crédito de los clientes.</span><span class="sxs-lookup"><span data-stu-id="da02c-108">If you carry out online transactions, you want to protect the credit card information of your customers.</span></span> <span data-ttu-id="da02c-109">Si trabaja en una empresa incluida en el índice Fortune 500, tendrá que mantener a los usuarios malintencionados alejados de las redes.</span><span class="sxs-lookup"><span data-stu-id="da02c-109">If you work for a Fortune 500 company, you want to keep malicious users away from your networks.</span></span> <span data-ttu-id="da02c-110">Si es usuario de un equipo de escritorio, no debe permitir que los virus y gusanos dañen los datos y limiten su capacidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="da02c-110">If you are a desktop user, you want to keep viruses and worms from damaging your data and limiting your ability to do your work.</span></span> <span data-ttu-id="da02c-111">Casi a diario, se reciben noticias de nuevas vulnerabilidades de software; de nuevos gusanos y virus que se extienden con mayor rapidez y que son más difíciles de erradicar y más dañinos que los anteriores; así como de sitios Web de empresas que son objeto de ataques de usuarios malintencionados.</span><span class="sxs-lookup"><span data-stu-id="da02c-111">Almost every day you hear or read about new software vulnerabilities; about new worms and viruses that are faster spreading, harder to eradicate, and more damaging than the previous ones; and about the Web sites of companies being defaced by malicious users.</span></span> <span data-ttu-id="da02c-112">Lo que su empresa tiene: grandes o pequeños, unos pocos clientes o millones de clientes, un equipo o cientos de equipos, necesita mantener los usuarios malintencionados y programas (como virus y gusanos) pongan en peligro los datos, los equipos y capacidad para realizar su trabajo.</span><span class="sxs-lookup"><span data-stu-id="da02c-112">Whatever your business is—large or small, a few customers or millions of customers, one computer or hundreds of computers—you need to keep malicious users and programs (viruses, worms) from compromising your data, computers, and ability to do your job.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da02c-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="da02c-113">In This Section</span></span>  
  
-   [<span data-ttu-id="da02c-114">Casos prácticos de seguridad: La compañía A</span><span class="sxs-lookup"><span data-stu-id="da02c-114">Security Case Studies: Company A</span></span>](../core/security-case-studies-company-a.md)  
  
-   [<span data-ttu-id="da02c-115">Casos prácticos de seguridad: La compañía B</span><span class="sxs-lookup"><span data-stu-id="da02c-115">Security Case Studies: Company B</span></span>](../core/security-case-studies-company-b.md)  
  
-   [<span data-ttu-id="da02c-116">Análisis de modelo de amenazas</span><span class="sxs-lookup"><span data-stu-id="da02c-116">Threat Model Analysis</span></span>](../core/threat-model-analysis.md)  
  
-   [<span data-ttu-id="da02c-117">Arquitecturas de ejemplo para pequeñas y medianas empresas</span><span class="sxs-lookup"><span data-stu-id="da02c-117">Sample Architectures for Small & Medium-Sized Companies</span></span>](../core/sample-architectures-for-small-medium-sized-companies.md)  
  
-   [<span data-ttu-id="da02c-118">Escenarios de ejemplo para el análisis de modelo de amenaza</span><span class="sxs-lookup"><span data-stu-id="da02c-118">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)