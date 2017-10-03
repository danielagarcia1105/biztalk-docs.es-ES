---
title: "Cómo usar el agente de administración de ENTSSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c89b494-db12-4d2a-a030-6acd34489cab
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c0f7d2c04a2707cf965f64ff7a559d8642a12c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-entsso-management-agent"></a>Uso del agente de administración ENTSSO
Esta versión de Enterprise Single Sign-On (SSO) contiene un agente de administración para Microsoft Identity Integration Server (MIIS), que integra SSO empresarial con las capacidades de sincronización de cuentas de MIIS. Esto habilita al administrador de MIIS para administrar asignaciones de SSO en la base de datos de SSO.  
  
 En SSO empresarial, se crean asignaciones entre cuentas de dominio de Windows (*ombreDeUsuario*) y credenciales externas. Si tiene un agente de administración de Active Directory y el agente de administración para el origen de datos externo (ejemplo: RACF MA), puede usar el SSO empresarial (ENTSSO MA) del agente de administración para administrar las asignaciones en la base de datos de SSO. ENTSSO MA es un *exportación basada en llamadas* solo agente de administración.  
  
 Configure el agente de administración en tres partes independientes:  
  
-   Un archivo de configuración (ENTSSO.xml)  
  
-   La interfaz de usuario de MIIS  
  
-   La interfaz de usuario de ENTSSO  
  
 Los temas de esta sección describen el proceso de configuración.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar el archivo XML.](../core/configuring-the-xml-file.md)  
  
-   [Cómo configurar MIIS para ENTSSO MA](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [Cómo configurar ENTSSO para la sincronización de contraseña MIIS](../core/how-to-configure-entsso-for-miis-password-sync.md)