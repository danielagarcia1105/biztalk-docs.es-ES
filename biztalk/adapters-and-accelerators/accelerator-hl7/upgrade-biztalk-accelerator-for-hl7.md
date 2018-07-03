---
title: Actualizar el Acelerador de BizTalk para HL7 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91b6747f-e560-4cf8-99b5-af0d150599bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 245d59e54a39cb77a71fc546920542619a4aeb3f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977645"
---
# <a name="upgrade-biztalk-accelerator-for-hl7"></a>Actualizar el Acelerador de BizTalk para HL7
Información general sobre el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] proceso de actualización. 

<a name="BKMK_BeforeUpgrade"></a>   
## <a name="before-you-upgrade"></a>Antes de realizar la actualización  

- El usuario que ejecuta la actualización debe ser miembro del grupo Administradores de BizTalk.  

- El servicio de SQL Server (MSSQLSERVER) debe estar ejecutándose al realizar una actualización.  

- No ejecute una instalación silenciosa para actualizar.  

- Cuando se actualiza, el programa de instalación migra existente [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] información de configuración a la versión más reciente.  

- Cuando se actualiza, las claves del registro y las bases de datos se copian automáticamente.  

- Los archivos en el  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7 carpeta se actualizan.  

> [!IMPORTANT]
>  La actualización no crea una nueva carpeta para los archivos actualizados, ni tampoco cambia el nombre de la carpeta existente.  

<a name="BKMK_UpgradePaths"></a>   
## <a name="supported-upgrade-paths"></a>Rutas de actualización admitidas  
 En la tabla siguiente se enumera admitidos [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] versiones que se pueden actualizar. "Sí" significa que el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] versión puede actualizarse. "No" significa que el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] versión no se puede actualizar. Si el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] versión no aparece, no se puede actualizar esa versión.  


|                                                                                              | [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)] | BizTalk Server 2013 |
|----------------------------------------------------------------------------------------------|------------------------------------------------------|-------------------------------------------------------|---------------------|
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2013 |                         Sí                          |                          Sí                          |         no          |
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2010 |                          no                          |                          Sí                          |         Sí         |

<a name="BKMK_UpgradeSteps"></a>   
## <a name="upgrade-steps"></a>Pasos de la actualización  

1. Actualizar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].   

2. Copia de seguridad de la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] bases de datos y su HL7 los esquemas de mensajes.  

3. Copia de seguridad de los archivos en el ***\<unidad\>*:\Program de programa\Microsoft BizTalk Accelerator para HL7** carpeta que ha cambiado. Por ejemplo, realizar una copia de seguridad de archivos en el SDK.  

4. Instalar la actualización adecuada para su versión de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:  

   -   Si actualiza desde BTAHL7 2010, instale **HL72010Patch.msp**.  

   -   Si actualiza desde BTAHL7 2013, instale **HL72013Patch.msp**.  


5. Ejecute el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] el programa de instalación. Consulte [instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).  

6. Implementar el nuevo BTAHL7V2*x*proyecto común.  

7. Volver a implementar todos los demás ensamblados.  

8. Recompile los proyectos y ensamblados que tengan una referencia a uno o varios de los ensamblados de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]. Mediante **BTSTask.exe** en \< *unidad*\>: BizTalk Server \Program Files\Microsoft \<versión\>, manualmente volver a implementar estos proyectos.  

9. Reinicie el servicio [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] .  

<a name="BKMK_UpgradeMulti"></a>   
## <a name="upgrading-in-a-multi-server-environment"></a>Realizar una actualización en un entorno multiservidor  
 En un servidor de múltiples [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] entorno, actualización [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]s y después actualiza el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] en todos los servidores. Migre los servidores en este orden:  

-   Servidor que hospeda el grupo de BizTalk  

-   Cada nodo de procesamiento  

-   Servidor del portal de BAM  

## <a name="see-also"></a>Vea también  
 [Instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)