---
title: Solución de problemas de errores de validación de mensajes mediante la visualización del contenido Hexadecimal de mensajes suspendidos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf14cd9-2d4b-43a3-9738-52bfd879e1e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f7dc0f24a85f206831e3706bd03f2206aaa2c15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279572"
---
# <a name="troubleshooting-message-validation-failures-by-viewing-the-hexadecimal-contents-of-suspended-messages"></a><span data-ttu-id="d9448-102">Solucionar problemas relacionados con errores de validación de mensajes mediante la visualización del contenido hexadecimal de los mensajes suspendidos</span><span class="sxs-lookup"><span data-stu-id="d9448-102">Troubleshooting Message Validation Failures by Viewing the Hexadecimal Contents of Suspended Messages</span></span>
<span data-ttu-id="d9448-103">Si un mensaje se suspende debido a errores de validación, puede resultar útil ver la representación hexadecimal de las partes del mensaje para determinar la causa del error de validación.</span><span class="sxs-lookup"><span data-stu-id="d9448-103">If a message is suspended due to validation failures, it may be helpful to view the hexadecimal representation of the message parts to determine the cause of the validation failure.</span></span> <span data-ttu-id="d9448-104">En este tema se enumeran los pasos que pueden llevarse a cabo para ver la representación hexadecimal de las partes de un mensaje suspendido.</span><span class="sxs-lookup"><span data-stu-id="d9448-104">This topic lists steps that can be followed to view the hexadecimal representation of the parts of a suspended message.</span></span>  
  
## <a name="use-the-message-details-dialog-box-to-view-message-parts"></a><span data-ttu-id="d9448-105">Usar el cuadro de diálogo Detalles del mensaje para ver las partes de los mensajes</span><span class="sxs-lookup"><span data-stu-id="d9448-105">Use the Message Details dialog box to view message parts</span></span>  
 <span data-ttu-id="d9448-106">Para ver la representación hexadecimal de las partes de un mensaje, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d9448-106">Follow these steps to view the hexadecimal representation of message parts:</span></span>  
  
1.  <span data-ttu-id="d9448-107">Use la **consulta** pestaña en la consola de administración de BizTalk para devolver un conjunto de resultados con uno o varios mensajes suspendidos.</span><span class="sxs-lookup"><span data-stu-id="d9448-107">Use the **Query** tab in the BizTalk Administration Console to return a result set with one or more suspended messages.</span></span> <span data-ttu-id="d9448-108">Vea [cómo buscar mensajes](../core/how-to-search-for-messages.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d9448-108">See [How to Search for Messages](../core/how-to-search-for-messages.md) for more information.</span></span>  
  
2.  <span data-ttu-id="d9448-109">Haga doble clic en el mensaje suspendido que desea investigar para mostrar el **detalles del mensaje** cuadro de diálogo para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d9448-109">Double-click the suspended message that you want to investigate to display the **Message Details** dialog box for the message.</span></span>  
  
3.  <span data-ttu-id="d9448-110">Haga clic en una parte del mensaje en el panel izquierdo de la **detalles del mensaje** cuadro de diálogo para mostrar la parte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d9448-110">Click a message part in the left hand pane of the **Message Details** dialog box to display the message part.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d9448-111">Los mensajes pueden constar de 0, 1 o varias partes.</span><span class="sxs-lookup"><span data-stu-id="d9448-111">Messages may have 0, 1 or many message parts.</span></span> <span data-ttu-id="d9448-112">Los mensajes suelen tener una sola parte a la que se denomina "cuerpo".</span><span class="sxs-lookup"><span data-stu-id="d9448-112">Most often messages have single message part that is called "body".</span></span>  
  
4.  <span data-ttu-id="d9448-113">Haga clic en el **binario** en el panel derecho de la **detalles del mensaje** cuadro de diálogo para mostrar la representación hexadecimal de la parte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d9448-113">Click the **Binary** tab in the right hand pane of the **Message Details** dialog box to display the hexadecimal representation of the message part.</span></span>  
  
5.  <span data-ttu-id="d9448-114">Examine la representación hexadecimal de caracteres en las partes del mensaje para comprobar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9448-114">Check the hexadecimal representation of characters in message parts for the following:</span></span>  
  
    -   <span data-ttu-id="d9448-115">Marca de orden de bytes no válida o que falta.</span><span class="sxs-lookup"><span data-stu-id="d9448-115">Missing or invalid byte order mark.</span></span> <span data-ttu-id="d9448-116">Para obtener más información sobre el orden de bytes sobre marcas, consulte [http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380).</span><span class="sxs-lookup"><span data-stu-id="d9448-116">For more information about byte order marks see [http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380).</span></span>  
  
    -   <span data-ttu-id="d9448-117">Diferencias entre la codificación de los saltos de línea en Unix y Windows.</span><span class="sxs-lookup"><span data-stu-id="d9448-117">Differences between the encoding of linebreaks in Unix and Windows.</span></span> <span data-ttu-id="d9448-118">Unix emplea el avance de línea hexadecimal (0A) para indicar un salto de línea, mientras que Windows utiliza tanto el retorno de carro hexadecimal (0D) como el avance de línea (0A) para indicarlo.</span><span class="sxs-lookup"><span data-stu-id="d9448-118">Unix uses hex linefeed (0A) to indicate a line break where Windows uses both hex carriage return (0D) and linefeed (0A) to indicate a line break.</span></span>  
  
    -   <span data-ttu-id="d9448-119">Caracteres de control no válidos en partes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d9448-119">Invalid control character(s) in message parts.</span></span> <span data-ttu-id="d9448-120">Los caracteres de control en partes del mensaje que no se muestran en la vista de texto pueden verse en la vista binaria.</span><span class="sxs-lookup"><span data-stu-id="d9448-120">Control characters in message parts that do not show up in the text view may be visible in the binary view.</span></span>  
  
    -   <span data-ttu-id="d9448-121">Caracteres nulos no válidos en la mitad de una parte del mensaje que pueden ocasionar que ésta se trunque.</span><span class="sxs-lookup"><span data-stu-id="d9448-121">Invalid nul character(s) in the middle of a message part can cause the message part to be truncated.</span></span> <span data-ttu-id="d9448-122">El carácter nulo se representa como (00) en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="d9448-122">The nul character is represented as hex (00).</span></span>  
  
    -   <span data-ttu-id="d9448-123">Desplazamiento de caracteres no válido en archivos sin formato posicionales.</span><span class="sxs-lookup"><span data-stu-id="d9448-123">Invalid character offset in positional flat files.</span></span> <span data-ttu-id="d9448-124">Observe la representación hexadecimal de una parte del mensaje para ver el desplazamiento de datos en un archivo sin formato posicional.</span><span class="sxs-lookup"><span data-stu-id="d9448-124">Display the hexadecimal representation of a message part to view the offset of data in a positional flat file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9448-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9448-125">See Also</span></span>  
 [<span data-ttu-id="d9448-126">Investigación de orquestación, puerto y errores de mensaje</span><span class="sxs-lookup"><span data-stu-id="d9448-126">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)