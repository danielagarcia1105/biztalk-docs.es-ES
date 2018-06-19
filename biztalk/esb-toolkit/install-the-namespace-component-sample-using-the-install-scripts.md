---
title: Instalar el ejemplo de componente de Namespace con los Scripts de instalación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66046ef4-91a2-4fe7-93ad-3b8137294411
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3e3fc23d938fb9fc209124f7c9beff001d66771
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973018"
---
# <a name="install-the-namespace-component-sample-using-the-install-scripts"></a><span data-ttu-id="3fbc6-102">Instalar el ejemplo de componente de Namespace con los Scripts de instalación</span><span class="sxs-lookup"><span data-stu-id="3fbc6-102">Install the Namespace Component Sample Using the Install Scripts</span></span>
<span data-ttu-id="3fbc6-103">En esta sección se describe cómo puede instalar el ejemplo del componente de Namespace desde el archivo de Windows Installer proporcionado con la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fbc6-103">This section describes how you can install the Namespace Component sample from the Windows Installer file provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="3fbc6-104">**Para instalar el ejemplo del componente de Namespace de las secuencias de comandos de instalación**</span><span class="sxs-lookup"><span data-stu-id="3fbc6-104">**To install the Namespace Component sample from the install scripts**</span></span>  
  
1.  <span data-ttu-id="3fbc6-105">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3fbc6-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="3fbc6-106">En el **ejecutar** cuadro de diálogo, escriba **cmd**, y, a continuación, presione ENTRAR para abrir un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3fbc6-106">In the **Run** dialog box, type **cmd**, and then press ENTER to open a command prompt.</span></span>  
  
3.  <span data-ttu-id="3fbc6-107">Ejecute el comando siguiente, reemplazando el  *\<ruta de acceso\>*  parámetro con la ruta de acceso completa al archivo .cmd que desea instalar (la ruta predeterminada en esta versión es \Source\Samples\Namepace\Install\Scripts\\):</span><span class="sxs-lookup"><span data-stu-id="3fbc6-107">Run the following command, replacing the *\<path\>* parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\Namepace\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```