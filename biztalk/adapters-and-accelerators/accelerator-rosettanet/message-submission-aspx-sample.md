---
title: Ejemplo ASPX de envío de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8358f849-231f-432c-9fc2-6efdcf95580d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fb7d90485014a62ed9010590d27a79ecd925c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207204"
---
# <a name="message-submission-aspx-sample"></a><span data-ttu-id="20cc6-102">Ejemplo de ASPX de envío de mensajes</span><span class="sxs-lookup"><span data-stu-id="20cc6-102">Message Submission ASPX Sample</span></span>
<span data-ttu-id="20cc6-103">En este tema se proporciona código de .aspx de ejemplo que puede usar para enviar el contenido del servicio a un proceso privado.</span><span class="sxs-lookup"><span data-stu-id="20cc6-103">This topic provides sample .aspx code that you can use to submit service content to a private process.</span></span> <span data-ttu-id="20cc6-104">Puede usar este código .aspx en lugar de una aplicación de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="20cc6-104">You can use this .aspx code instead of a line-of-business (LOB) application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="20cc6-105">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="20cc6-105">Demonstrates</span></span>  
 <span data-ttu-id="20cc6-106">Este código muestra cómo llamar a la `SubmitRNIF` método para enviar un mensaje, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="20cc6-106">This code demonstrates how to call the `SubmitRNIF` method to submit a message, including the following:</span></span>  
  
-   <span data-ttu-id="20cc6-107">Establecer la entrada de parámetros de mensaje desde una aplicación</span><span class="sxs-lookup"><span data-stu-id="20cc6-107">Setting message parameters input from an application</span></span>  
  
-   <span data-ttu-id="20cc6-108">Configuración de la categoría de mensaje</span><span class="sxs-lookup"><span data-stu-id="20cc6-108">Setting the message category</span></span>  
  
-   <span data-ttu-id="20cc6-109">Generar una instancia de proceso de interfaz de socio (PIP) para el mensaje si el valor enviado es nulo o está vacío</span><span class="sxs-lookup"><span data-stu-id="20cc6-109">Generating a Partner Interface Process (PIP) instance for the message if the submitted value is null or empty</span></span>  
  
-   <span data-ttu-id="20cc6-110">La generación de la matriz de archivos de entrada de datos adjuntos y comentarios</span><span class="sxs-lookup"><span data-stu-id="20cc6-110">Generating the input attachment files array and remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="20cc6-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="20cc6-111">Example</span></span>  
 <span data-ttu-id="20cc6-112">Este código acepta la entrada desde una aplicación front-end, como un explorador, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]®, o [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® Word y genera el documento XML que puede utilizar el proceso privado de iniciador.</span><span class="sxs-lookup"><span data-stu-id="20cc6-112">This code accepts input from a front-end application, such as a browser, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]®, or [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® Word, and generates the XML document that the initiator private process can consume.</span></span>  
  
 <span data-ttu-id="20cc6-113">La utilidad de LOBWebApplication incluye el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="20cc6-113">The LOBWebApplication utility includes the following code.</span></span> <span data-ttu-id="20cc6-114">Para obtener más información, consulte [LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md).</span><span class="sxs-lookup"><span data-stu-id="20cc6-114">For more information, see [LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md).</span></span>  
  
```  
using System;  
using System.IO;  
using System.Text;  
using System.Data;  
using System.Drawing;  
using System.Collections;  
using System.ComponentModel;  
using System.Web;  
using System.Web.UI;  
using System.Web.SessionState;  
using System.Web.UI.WebControls;  
using System.Web.UI.HtmlControls;  
using Microsoft.Solutions.BTARN.SubmitRNIF;  
  
namespace Microsoft.Solutions.BTARN.SDK  
{  
      /// <summary>  
      /// Calls SubmitRNIF to submit service content to the BTARN private process.  
      /// </summary>  
      public class AspxLobApplication : System.Web.UI.Page  
      {  
            private void Page_Load(object sender, System.EventArgs e)  
            {  
                  Request.ValidateInput();  
  
                  string sPipCode=Request["PipCode"];  
                  string sPipVersion=Request["PipVersion"];  
                  string sPipInstanceID=Request["PipInstanceID"];  
                  string sPipCategory=Request["PipCategory"];  
                  string sPipSource=Request["PipSource"];  
                  string sPipDestination=Request["PipDestination"];  
                  string sFileName1=Request["FileName1"];  
                  string sFileName2=Request["FileName2"];  
                  string sRemark1=Request["Remark1"];  
                  string sRemark2=Request["Remark2"];  
                  string[] aInputFiles = new string[2];  
                  string[] aRemarks = new string[2];  
                  string sContent = Request["Textarea1"];  
  
                  SubmitRNIF.SubmitRNIF MessageSubmitter = new SubmitRNIF.SubmitRNIF();  
  
                  //The message category  
                  SubmitRNIF.SubmitRNIF.MessageCategory mc;  
                  if(sPipCategory.ToUpper() == "RESPONSE")   
                        mc=SubmitRNIF.SubmitRNIF.MessageCategory.Response;  
                  else  
                        mc=SubmitRNIF.SubmitRNIF.MessageCategory.Action;  
  
                  //Generate a PIP instance ID if the submitted value is null or empty  
                  if(sPipInstanceID.Length==0)  
                        sPipInstanceID=Guid.NewGuid().ToString();  
  
                  //Generate the input attachment files array and its associated remarks  
                  if(sFileName1!=null && sFileName1.Length>0) aInputFiles[0]=sFileName1;  
                  if(sFileName2!=null && sFileName2.Length>0) aInputFiles[1]=sFileName1;  
                  if(sRemark1!=null && sRemark1.Length>0) aRemarks[0]=sRemark1;  
                  if(sRemark2!=null && sRemark2.Length>0) aRemarks[1]=sRemark2;  
  
                  if(sFileName1==null && sFileName2==null)  
                        MessageSubmitter.SubmitMessage(mc, sPipSource, sPipDestination, sPipCode, sPipInstanceID, sPipVersion, sContent);  
                  else  
                        MessageSubmitter.SubmitMessage(mc, sPipSource, sPipDestination, sPipCode, sPipInstanceID, sPipVersion, sContent, aInputFiles);  
            }  
  
            #region Web Form Designer generated code  
...  
      }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="20cc6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="20cc6-115">See Also</span></span>  
 <span data-ttu-id="20cc6-116">[LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md) </span><span class="sxs-lookup"><span data-stu-id="20cc6-116">[LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md) </span></span>  
 [<span data-ttu-id="20cc6-117">Ejemplos de mensajería</span><span class="sxs-lookup"><span data-stu-id="20cc6-117">Messaging Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)