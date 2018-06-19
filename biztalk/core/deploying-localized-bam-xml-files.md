---
title: Implementar archivos de XML de BAM localizados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, unicode mapping
- unicode mapping [BAM]
ms.assetid: 8e7e3431-cd20-45db-b7f2-0df23e9df42b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3452f13569ca6a0c0bb5843995c07a15b30f4da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239316"
---
# <a name="deploying-localized-bam-xml-files"></a><span data-ttu-id="6449d-102">Implementar archivos XML de BAM localizados</span><span class="sxs-lookup"><span data-stu-id="6449d-102">Deploying Localized BAM XML Files</span></span>
<span data-ttu-id="6449d-103">Microsoft SQL Server Analysis Services admite asignaciones Unicode.</span><span class="sxs-lookup"><span data-stu-id="6449d-103">Microsoft SQL Server Analysis Services supports Unicode mapping.</span></span> <span data-ttu-id="6449d-104">Sin embargo, existen problemas conocidos de corrupción de caracteres en las asignaciones Unicode de Visual Basic y de SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="6449d-104">However, there are known character corruption issues with SQL Server Analysis Services and Visual Basic Unicode mapping.</span></span> <span data-ttu-id="6449d-105">En concreto, si la configuración regional no se ha definido con el idioma localizado correcto, cuando se produce la conversión de ANSI a Unicode, ésta se realiza con la información local incorrecta por lo que se producen daños en los caracteres.</span><span class="sxs-lookup"><span data-stu-id="6449d-105">Specifically, if the regional settings are not set to the correct localized language when the conversion from ANSI to Unicode occurs, the conversion is performed using the wrong locale information and character corruption occurs.</span></span>  
  
 <span data-ttu-id="6449d-106">Para implementar un archivo XML de definición de BAM correctamente, debe pasar su configuración regional a la región correcta antes de poder implementar un archivo XML de definición de BAM que contenga los caracteres localizados.</span><span class="sxs-lookup"><span data-stu-id="6449d-106">To deploy the BAM definition XML file successfully, you must switch your system locale to the correct locale before you can actually deploy a BAM definition XML file that contains localized characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6449d-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="6449d-107">See Also</span></span>  
 <span data-ttu-id="6449d-108">[Administración de BAM](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="6449d-108">[Managing BAM](../core/managing-bam.md) </span></span>  
 [<span data-ttu-id="6449d-109">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="6449d-109">BAM Management Utility</span></span>](../core/bam-management-utility.md)