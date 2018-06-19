---
title: Emitir y canjear un vale de inicio de sesión único | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a0323a6-cc31-460d-b64d-b4d8142c3855
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9988eedb545b3b1a348a5de6275b176abe2be7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261772"
---
# <a name="issuing-and-redeeming-a-single-sign-on-ticket"></a><span data-ttu-id="2b928-102">Emitir y canjear un vale de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="2b928-102">Issuing and Redeeming a Single Sign-On Ticket</span></span>
<span data-ttu-id="2b928-103">Después de vincular a un usuario con una aplicación afiliada, puede emitir vales para ayudar a garantizar la seguridad durante las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="2b928-103">After you link a user and an affiliate application, you can issue tickets to help ensure security while maintaining communications.</span></span> <span data-ttu-id="2b928-104">Single Sign-On vales funciona igual que otras tecnologías de control de vales: antes de enviar el mensaje de, anexe el vale de inicio de sesión único para el mensaje como una cadena.</span><span class="sxs-lookup"><span data-stu-id="2b928-104">Single Sign-On ticketing works just like other ticketing technologies: before sending the message off, you append the Single Sign-On ticket to the message as a string.</span></span> <span data-ttu-id="2b928-105">El servidor recibe el mensaje, descodifica el vale y utiliza la información como corresponda.</span><span class="sxs-lookup"><span data-stu-id="2b928-105">The server receives your message, decodes the ticket, and uses the information as appropriate.</span></span>  
  
### <a name="to-issue-a-single-sign-on-ticket"></a><span data-ttu-id="2b928-106">Para emitir un vale de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="2b928-106">To issue a Single Sign-On ticket</span></span>  
  
1.  <span data-ttu-id="2b928-107">Crear un nuevo objeto de vale con una llamada a I`SSOTicket`.</span><span class="sxs-lookup"><span data-stu-id="2b928-107">Create a new ticket object with a call to I`SSOTicket`.</span></span>  
  
2.  <span data-ttu-id="2b928-108">Emita el vale con una llamada a I`SSOTicket.IssueTicket`.</span><span class="sxs-lookup"><span data-stu-id="2b928-108">Issue the ticket with a call to I`SSOTicket.IssueTicket`.</span></span>  
  
### <a name="to-redeem-a-single-sign-on-ticket"></a><span data-ttu-id="2b928-109">Para canjear un vale de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="2b928-109">To redeem a Single Sign-On ticket</span></span>  
  
1.  <span data-ttu-id="2b928-110">Crear un nuevo objeto de vale con una llamada a I`SSOTicket`.</span><span class="sxs-lookup"><span data-stu-id="2b928-110">Create a new ticket object with a call to I`SSOTicket`.</span></span>  
  
2.  <span data-ttu-id="2b928-111">Canjee el vale con una llamada a I`SSOTicket.RedeemTicket`.</span><span class="sxs-lookup"><span data-stu-id="2b928-111">Redeem the ticket with a call to I`SSOTicket.RedeemTicket`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b928-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b928-112">See Also</span></span>  
 [<span data-ttu-id="2b928-113">Programar con Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="2b928-113">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)