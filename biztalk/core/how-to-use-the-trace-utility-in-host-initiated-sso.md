---
title: "Cómo usar la utilidad de seguimiento de Host para SSO iniciado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host initiated SSO, trace utility
- trace utility
ms.assetid: a53444d1-3f63-42a6-8ee6-b60ff9af9e41
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e00514515b31e79655fe457e1aa8682edf002183
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-trace-utility-in-host-initiated-sso"></a><span data-ttu-id="ee9b6-102">Cómo usar la utilidad de seguimiento de Host para SSO iniciado</span><span class="sxs-lookup"><span data-stu-id="ee9b6-102">How to Use the Trace Utility in Host Initiated SSO</span></span>
<span data-ttu-id="ee9b6-103">El seguimiento constituye el método principal para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="ee9b6-103">The primary method of troubleshooting is tracing.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="ee9b6-104">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="ee9b6-104">Tracing</span></span>  
 <span data-ttu-id="ee9b6-105">Utilice la línea de comandos de seguimiento para habilitar el seguimiento en SSO.</span><span class="sxs-lookup"><span data-stu-id="ee9b6-105">Use the Trace command line utility to enable tracing in SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee9b6-106">Para que este comando funcione, el archivo tracelog.exe debe encontrarse en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="ee9b6-106">For the trace command to function, the file tracelog.exe must be in the following directory:</span></span>  
>   
>  <span data-ttu-id="ee9b6-107">\<*unidad*>: \Program Files\Common Files\Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="ee9b6-107">\<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee9b6-108">Puede descargar este archivo en la siguiente ubicación: [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)</span><span class="sxs-lookup"><span data-stu-id="ee9b6-108">You can download this file from the following location: [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)</span></span>  
  
#### <a name="to-use-the-trace-utility"></a><span data-ttu-id="ee9b6-109">Para utilizar la utilidad de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ee9b6-109">To use the trace utility</span></span>  
  
1.  <span data-ttu-id="ee9b6-110">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ee9b6-110">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="ee9b6-111">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ee9b6-111">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="ee9b6-112">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="ee9b6-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="ee9b6-113">El valor predeterminado es \<unidad >: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="ee9b6-113">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="ee9b6-114">Tipo de **Trace – start – high** para establecer el nivel de seguimiento como alto y comenzar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ee9b6-114">Type **Trace –start –high** to set the tracing level to high and begin the trace.</span></span>  
  
5.  <span data-ttu-id="ee9b6-115">Ejecute el escenario con el SSO iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="ee9b6-115">Run the scenario with host initiated SSO.</span></span>  
  
6.  <span data-ttu-id="ee9b6-116">Tipo de **Trace – stop** para finalizar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ee9b6-116">Type **Trace –stop** to end the trace.</span></span> <span data-ttu-id="ee9b6-117">En el directorio anterior se generará un archivo .bin que podrá enviar a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="ee9b6-117">A .bin file is generated in the directory above, which you can send to Microsoft for analysis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee9b6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee9b6-118">See Also</span></span>  
 [<span data-ttu-id="ee9b6-119">SSO iniciado por host</span><span class="sxs-lookup"><span data-stu-id="ee9b6-119">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)