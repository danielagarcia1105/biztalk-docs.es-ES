---
title: Cómo actualizar la configuración de BAM mediante la utilidad de administración de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 714a834e-1879-4019-9b54-e511705bd67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 952c163e809ceff8f084e661b542752d30f18096
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019915"
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a>Cómo actualizar la configuración de BAM mediante la utilidad de administración de BAM
Los administradores pueden utilizar la utilidad de administración de BAM para actualizar una instalación de BAM existente.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe tener permisos de administrador en la base de datos de BAM que se está actualizando.  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a>Para actualizar la configuración de BAM mediante la utilidad de administración de BAM  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3. Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm update-config - FileName:\<archivo de configuración\>**, donde \< *archivo de configuración* \> es se sustituye por el nombre de su archivo de configuración de BAM. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)