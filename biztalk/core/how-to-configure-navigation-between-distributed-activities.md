---
title: "Cómo configurar la exploración entre distribuidas actividades | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f8faf0a-eb06-4383-932d-4106306d6cf3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ab210f5ab728134b406b5c4bdaf25a1ec6db1c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-navigation-between-distributed-activities"></a>Cómo configurar la exploración entre actividades distribuidas
La exploración distribuida permite a los usuarios ver actividades existentes en implementaciones de BAM remotas. Al habilitar la exploración distribuida, los usuarios del portal de BAM de un equipo serán capaces de ver actividades en el portal de BAM de otra implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 El procedimiento de este tema describe cómo habilitar la exploración distribuida en el siguiente escenario:  
  
-   Un departamento de ventas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementado en el equipo 1.  
  
-   Un departamento de envíos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementado en el equipo 2.  
  
-   Una vista denominada myBusinessView con una actividad denominada Datos de ventas implementada en el equipo 1.  
  
-   Una vista denominada myBusinessView con una actividad denominada Datos de envíos instalada en el equipo 2.  
  
-   Un usuario empresarial del departamento de ventas con una empresa necesita ver las actividades en ambos equipos.  
  
### <a name="how-to-set-up-distributed-navigation-for-remote-activities"></a>Cómo configurar la exploración distribuida para actividades remotas  
  
1.  El administrador del equipo 1 concede al usuario empresarial acceso a la vista myBusinessView en el equipo 1. Use el comando bm.exe, como se indica a continuación: **agregar-account - AccountName:\<nombre de la cuenta\> -View:** myBusinessView  
  
2.  El administrador del equipo 1 habilita la exploración distribuida ejecutando el comando enable-reference, como se indica a continuación: **bm.exe enable-reference - TargetServer:** Equipo2 **- TargetDatabase:\<destino base de datos\>**  
  
    > [!NOTE]
    >  Por lo general, la cuenta utilizada entre departamentos para el acceso a los servicios Web de BAM variará de un equipo a otro. Por lo tanto, en este escenario el administrador del equipo 1 debe agregar la cuenta de suplantación de servicios Web del equipo 1 a la función BAM_ManagementWS de la base de datos de importación principal de BAM para el equipo 2. Para obtener más información, vea "Ver y modificar las pertenencias a roles" en [http://go.microsoft.com/fwlink/?LinkId=66990](http://go.microsoft.com/fwlink/?LinkId=66990).  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
3.  El administrador del equipo 2 concede al usuario empresarial acceso a la vista myBusinessView en el equipo 2 utilizando el comando BM.exe como se indicó en el paso 1:  
  
## <a name="results-of-setting-up-distributed-navigation"></a>Resultados de la configuración de la exploración distribuida  
 Cuando se habilita la exploración distribuida, los usuarios agregados a las vistas de los dos equipos verán, en el panel Mis vistas del portal de inicio correspondiente, las actividades de las vistas implementadas en ellos. Cuando estos usuarios hacen clic en una actividad hospedada en una implementación remota, se les conduce directamente al portal en el que se hospeda esa actividad y se les permite verla como si estuviera en el portal predeterminado que les corresponde.  
  
> [!NOTE]
>  La exploración distribuida se puede habilitar en ambas direcciones. Si se sigue el procedimiento anterior en los dos equipos que comparten actividades remotas, se permite a los usuarios empresariales de cualquiera de los equipos utilizar la exploración distribuida.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la exploración distribuida de actividades remotas](../core/managing-distributed-navigation-of-remote-activities.md)   
 [Portal de BAM](../core/bam-portal.md)