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
# <a name="deploying-localized-bam-xml-files"></a>Implementar archivos XML de BAM localizados
Microsoft SQL Server Analysis Services admite asignaciones Unicode. Sin embargo, existen problemas conocidos de corrupción de caracteres en las asignaciones Unicode de Visual Basic y de SQL Server Analysis Services. En concreto, si la configuración regional no se ha definido con el idioma localizado correcto, cuando se produce la conversión de ANSI a Unicode, ésta se realiza con la información local incorrecta por lo que se producen daños en los caracteres.  
  
 Para implementar un archivo XML de definición de BAM correctamente, debe pasar su configuración regional a la región correcta antes de poder implementar un archivo XML de definición de BAM que contenga los caracteres localizados.  
  
## <a name="see-also"></a>Vea también  
 [Administración de BAM](../core/managing-bam.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)