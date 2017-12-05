---
title: Actualizar el Acelerador de BizTalk para HL7 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91b6747f-e560-4cf8-99b5-af0d150599bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4df85c965943f2f2c916fef6b558f98caf2175f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="upgrade-biztalk-accelerator-for-hl7"></a>Actualizar el Acelerador de BizTalk para HL7
Información general sobre la [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] proceso de actualización. 
  
<a name="BKMK_BeforeUpgrade"></a>   
## <a name="before-you-upgrade"></a>Antes de realizar la actualización  
  
-   El usuario que ejecuta la actualización debe ser miembro del grupo Administradores de BizTalk.  
  
-   El servicio de SQL Server (MSSQLSERVER) debe estar ejecutándose al realizar una actualización.  
  
-   No ejecute una instalación silenciosa para actualizar.  
  
-   Cuando se actualiza, el programa de instalación migra existente [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] información de configuración a la versión más reciente.  
  
-   Cuando se actualiza, las claves del registro y las bases de datos se hacen copias de seguridad.  
  
-   Los archivos de la  *\<unidad\>*: \Program BizTalk \<versión\> Acelerador para HL7 carpeta se actualizan.  
  
> [!IMPORTANT]
>  La actualización no crea una nueva carpeta para los archivos actualizados, ni tampoco cambia el nombre de la carpeta existente.  
  
<a name="BKMK_UpgradePaths"></a>   
## <a name="supported-upgrade-paths"></a>Rutas de actualización admitidas  
 En la tabla siguiente se enumera los compatibles [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] versiones que se pueden actualizar. "Sí" significa la [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] versión se puede actualizar. "No" significa que el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] no se puede actualizar la versión. Si el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] versión no aparece, no se puede actualizar esa versión.  

||[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]|BizTalk Server 2013|
|---|---|---|---|  
|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2013|Sí|Sí|No|  
|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2010|No|Sí|Sí|  

<a name="BKMK_UpgradeSteps"></a>   
## <a name="upgrade-steps"></a>Pasos de la actualización  
  
1.  Actualizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].   
  
2.  Copia de seguridad el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] bases de datos y su HL7 esquemas de mensajes.  
  
3.  Los archivos de copia de seguridad la   ***\<unidad\>*: \Program Acelerador de BizTalk para HL7** carpeta que ha cambiado. Por ejemplo, realice una copia archivos en el SDK.  
  
4.  Instalar la actualización adecuada para su versión de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:  
  
    -   Si actualiza desde BTAHL7 2010, instale **HL72010Patch.msp**.  
  
    -   Si actualiza desde BTAHL7 2013, instale **HL72013Patch.msp**.  
    
  
5.  Ejecute el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] el programa de instalación. Vea [instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).  
  
6.  Implementar la nueva BTAHL7V2*x*proyecto común.  
  
7.  Volver a implementar todos los demás ensamblados.  
  
8.  Recompile los proyectos y ensamblados que tengan una referencia a uno o varios de los ensamblados de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. Usar **BTSTask.exe** en \< *unidad*\>: \Program BizTalk Server \<versión\>, manualmente volver a implementar estos proyectos.  
  
9. Reinicie el servicio [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] .  
  
<a name="BKMK_UpgradeMulti"></a>   
## <a name="upgrading-in-a-multi-server-environment"></a>Realizar una actualización en un entorno de varios servidores  
 En un servidor de varios [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] entorno, actualización [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]s y después actualiza el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] en todos los servidores. Migre los servidores en este orden:  
  
-   Servidor que hospeda el grupo de BizTalk  
  
-   Cada nodo de procesamiento  
  
-   Servidor del portal de BAM  
  
## <a name="see-also"></a>Vea también  
 [Instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)