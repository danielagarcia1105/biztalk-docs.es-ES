---
title: "Instalación de la administración de excepciones ejemplos de uso de secuencias de comandos de instalación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ba65a4b-5fe1-4e17-b979-c3d380b526d6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03af6a8317aa9b2dd3d26bf0204553401fc8978e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="installing-the-exception-management-samples-using-install-scripts"></a><span data-ttu-id="a8ca2-102">Instalar los ejemplos de administración de la excepción mediante secuencias de comandos de instalación</span><span class="sxs-lookup"><span data-stu-id="a8ca2-102">Installing the Exception Management Samples Using Install Scripts</span></span>
<span data-ttu-id="a8ca2-103">En esta sección se describe cómo puede instalar los ejemplos de administración de excepciones de las secuencias de comandos de instalación proporcionadas con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8ca2-103">This section describes how you can install the Exception Management samples from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="a8ca2-104">**Para instalar los ejemplos de administración de excepciones de ESB de las secuencias de comandos de instalación**</span><span class="sxs-lookup"><span data-stu-id="a8ca2-104">**To install the ESB Exception Management samples from the install scripts**</span></span>  
  
1.  <span data-ttu-id="a8ca2-105">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a8ca2-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="a8ca2-106">En el **ejecutar** cuadro de diálogo, escriba **cmd**, y, a continuación, presione ENTRAR para abrir un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a8ca2-106">In the **Run** dialog box, type **cmd**, and then press ENTER to open a command prompt.</span></span>  
  
3.  <span data-ttu-id="a8ca2-107">Ejecute el comando siguiente, reemplazando el  *\<ruta de acceso\>*  parámetro con la ruta de acceso completa al archivo .cmd que desea instalar (la ruta de acceso predeterminada y el nombre de esta versión es \Source\Samples\Exception Handling\ Install\Scripts\\):</span><span class="sxs-lookup"><span data-stu-id="a8ca2-107">Run the following command, replacing the *\<path\>* parameter with the full path to the .cmd file you want to install (the default path and name in this release is \Source\Samples\Exception Handling\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```