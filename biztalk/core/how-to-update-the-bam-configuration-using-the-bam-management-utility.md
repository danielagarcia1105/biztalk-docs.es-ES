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
ms.openlocfilehash: b08209d3b3a1555bbc674e469ea9f8a4b1f81a9d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a>Cómo actualizar la configuración de BAM mediante la utilidad de administración de BAM
Los administradores pueden utilizar la utilidad de administración de BAM para actualizar una instalación de BAM existente.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe tener permisos de administrador en la base de datos de BAM que se está actualizando.  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a>Para actualizar la configuración de BAM mediante la utilidad de administración de BAM  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm update-config - FileName:\<el archivo de configuración\>**, donde \< *archivo de configuración* \> es se sustituye por el nombre de su archivo de configuración de BAM. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)