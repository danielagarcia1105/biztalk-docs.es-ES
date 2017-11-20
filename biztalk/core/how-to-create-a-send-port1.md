---
title: "Cómo crear un envío Port1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: bf32e9f5-ebed-43d2-b9a9-6ab91925d973
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf49b16da34c5341059db34d6874b7099ab54df6
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-a-send-port"></a><span data-ttu-id="b30d2-102">Cómo crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="b30d2-102">How to Create a Send Port</span></span>
<span data-ttu-id="b30d2-103">Use el procedimiento siguiente para crear puertos de envío de BizTalk Server para JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="b30d2-103">Use the following procedure to create BizTalk Server send ports for JD Edwards EnterpriseOne.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="b30d2-104">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="b30d2-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="b30d2-105">Haga clic con el botón secundario en el nodo Puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="b30d2-105">Right-click the Send Ports node.</span></span>  
  
2.  <span data-ttu-id="b30d2-106">Haga clic en **agregar puerto de envío**.</span><span class="sxs-lookup"><span data-stu-id="b30d2-106">Click **Add Send Port**.</span></span>  
  
3.  <span data-ttu-id="b30d2-107">En el **crear nuevo puerto de envío** cuadro de diálogo, seleccione **puerto de petición-respuesta estático** desde el **especificar el tipo de puerto de envío** lista y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b30d2-107">In the **Create New Send Port** dialog box, select **Static Solicit-Response Port** from the **Specify the type of Send Port** list, and click **OK**.</span></span>  
  
     <span data-ttu-id="b30d2-108">El **propiedades de puerto de envío de petición-respuesta estático** abre la ventana.</span><span class="sxs-lookup"><span data-stu-id="b30d2-108">The **Static Solicit-Response Send Port Properties** window opens.</span></span>  
  
4.  <span data-ttu-id="b30d2-109">Escriba un nombre para el puerto de envío, por ejemplo, `SSOSendToJDEEntOne`.</span><span class="sxs-lookup"><span data-stu-id="b30d2-109">Type a name for the send port, for example, `SSOSendToJDEEntOne`.</span></span>  
  
5.  <span data-ttu-id="b30d2-110">Haga clic en **transporte** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b30d2-110">Click **Transport** in the left pane.</span></span>  
  
6.  <span data-ttu-id="b30d2-111">Haga clic en **tipo de transporte**y seleccione **JDEEntOne**.</span><span class="sxs-lookup"><span data-stu-id="b30d2-111">Click **Transport Type**, and select **JDEEntOne**.</span></span>  
  
7.  <span data-ttu-id="b30d2-112">Seleccione el **dirección (URI)**y haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="b30d2-112">Select the **Address (URI)**, and click the ellipsis (…) button.</span></span>  
  
     <span data-ttu-id="b30d2-113">JD Edwards EnterpriseOne **propiedades de transporte** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b30d2-113">The JD Edwards EnterpriseOne **Transport Properties** dialog box appears.</span></span>  
  
8.  <span data-ttu-id="b30d2-114">Tipo de `myJDEEntOneSSO` para el **nombre lógico del sistema**.</span><span class="sxs-lookup"><span data-stu-id="b30d2-114">Type `myJDEEntOneSSO` for the **Logical System Name**.</span></span>  
  
9. <span data-ttu-id="b30d2-115">Seleccione **Sí** para **usar SSO**.</span><span class="sxs-lookup"><span data-stu-id="b30d2-115">Select **Yes** for **Use SSO**.</span></span>  
  
10. <span data-ttu-id="b30d2-116">En la lista desplegable, seleccione la aplicación afiliada al inicio de sesión único (SSO) que creó para representar el sistema JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="b30d2-116">In the drop-down list, select the Single Sign-On (SSO) affiliate application that you created to represent the JD Edwards EnterpriseOne system.</span></span>  
  
     <span data-ttu-id="b30d2-117">Haga clic en **Aceptar** para confirmar la información que especificó.</span><span class="sxs-lookup"><span data-stu-id="b30d2-117">Click **OK** to confirm the information you entered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b30d2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b30d2-118">See Also</span></span>  
 <span data-ttu-id="b30d2-119">[Creación de aplicaciones afiliadas](../core/creating-affiliate-applications4.md) </span><span class="sxs-lookup"><span data-stu-id="b30d2-119">[Creating Affiliate Applications](../core/creating-affiliate-applications4.md) </span></span>  
 [<span data-ttu-id="b30d2-120">Seguridad del adaptador de BizTalk para JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="b30d2-120">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)