---
title: "Cómo actualizar la configuración de BAM mediante la utilidad de administración de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 714a834e-1879-4019-9b54-e511705bd67a
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee5958120e364cc0c2661ead6100bd2ba5502226
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a>Cómo actualizar la configuración de BAM mediante la utilidad de administración de BAM
Los administradores pueden utilizar la utilidad de administración de BAM para actualizar una instalación de BAM existente.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe tener permisos de administrador en la base de datos de BAM que se está actualizando.  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a>Para actualizar la configuración de BAM mediante la utilidad de administración de BAM  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm update-config - FileName:\<el archivo de configuración >**, donde \< *archivo de configuración*> se sustituye por el nombre de la BAM archivo de configuración. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)