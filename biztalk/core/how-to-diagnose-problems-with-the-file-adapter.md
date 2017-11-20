---
title: "Cómo diagnosticar problemas con el adaptador de archivo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f06089a5-4747-4879-a796-157088868dba
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0481a3abdf497c093a87d7d74ea0356c7cad0d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-file-adapter"></a><span data-ttu-id="e9a27-102">Cómo diagnosticar problemas con el adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="e9a27-102">How to Diagnose Problems with the File Adapter</span></span>
<span data-ttu-id="e9a27-103">Esta sección contiene los pasos que pueden seguirse para ayudar al diagnóstico de problemas con el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="e9a27-103">This section contains steps that can be followed to help diagnose problems with the File adapter.</span></span>  
  
### <a name="run-the-filemon-utility-to-diagnose-errors-that-occur-using-the-file-receive-or-file-send-adapter"></a><span data-ttu-id="e9a27-104">Ejecutar la utilidad FileMon para diagnosticar errores que se producen al utilizar el adaptador de recepción de archivos o el adaptador de envío de archivos</span><span class="sxs-lookup"><span data-stu-id="e9a27-104">Run the FileMon Utility to diagnose errors that occur using the File Receive or File Send Adapter</span></span>  
  
1.  <span data-ttu-id="e9a27-105">Descargar la utilidad FileMon de [www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235).</span><span class="sxs-lookup"><span data-stu-id="e9a27-105">Download the FileMon utility from [www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235).</span></span>  
  
2.  <span data-ttu-id="e9a27-106">Instale la utilidad Filemon en el servidor que aloja la carpeta o el recurso compartido que va a ser leído o escrito por el adaptador de archivos.</span><span class="sxs-lookup"><span data-stu-id="e9a27-106">Install the Filemon utility on the server that hosts the folder or share that is being read from or written to by the File Adapter.</span></span>  
  
3.  <span data-ttu-id="e9a27-107">Inicie la utilidad Filemon y aplique un filtro para supervisar solo los accesos a archivos que va a crear la instancia de host de BizTalk que los controles de adaptadores de archivos van a ejecutar en ellos (por ejemplo, BTSNTSvc.exe).</span><span class="sxs-lookup"><span data-stu-id="e9a27-107">Launch the Filemon utility and apply a filter to monitor only file accesses that are being made by the BizTalk Host instance that the file adapter handlers are running in (for example BTSNTSvc.exe).</span></span>  
  
4.  <span data-ttu-id="e9a27-108">Ejecute el escenario que ha causado el problema.</span><span class="sxs-lookup"><span data-stu-id="e9a27-108">Run the scenario that caused the problem.</span></span>  
  
5.  <span data-ttu-id="e9a27-109">Deshabilite el archivo que controla en la utilidad Filemon y, a continuación, guarde el archivo de registro generado en el disco.</span><span class="sxs-lookup"><span data-stu-id="e9a27-109">Disable file monitoring in the Filemon utility, then save the generated log file to disk.</span></span>  
  
6.  <span data-ttu-id="e9a27-110">Revise el archivo de registro generado para comprobar los errores.</span><span class="sxs-lookup"><span data-stu-id="e9a27-110">Review the generated log file for any errors.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e9a27-111">FileMon no es compatible con Microsoft y Microsoft no garantiza la idoneidad de este programa.</span><span class="sxs-lookup"><span data-stu-id="e9a27-111">FileMon is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="e9a27-112">La utilización de este programa queda bajo su propia responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="e9a27-112">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a27-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9a27-113">See Also</span></span>  
 <span data-ttu-id="e9a27-114">[Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="e9a27-114">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="e9a27-115">Solucionar problemas del adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="e9a27-115">Troubleshooting the File Adapter</span></span>](../core/troubleshooting-the-file-adapter.md)