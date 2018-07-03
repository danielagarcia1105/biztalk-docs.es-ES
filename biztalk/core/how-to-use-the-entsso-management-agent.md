---
title: Cómo usar el agente de administración de ENTSSO | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c89b494-db12-4d2a-a030-6acd34489cab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68c354f2250e9abc6a02ea52f4b7c106f57144e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018480"
---
# <a name="how-to-use-the-entsso-management-agent"></a>Uso del agente de administración ENTSSO
Esta versión de Enterprise Single Sign-On (SSO) contiene un agente de administración para Microsoft Identity Integration Server (MIIS), que integra SSO empresarial con las capacidades de sincronización de cuentas de MIIS. Esto habilita al administrador de MIIS para administrar asignaciones de SSO en la base de datos de SSO.  
  
 En SSO empresarial, las asignaciones se crean entre cuentas de dominio de Windows (*nombreDominio\nombreUsuario*) y credenciales externas. Si tiene un agente de administración de Active Directory y el agente de administración para el origen de datos externo (ejemplo: RACF MA), puede usar el SSO empresarial (ENTSSO MA) del agente de administración para administrar las asignaciones en la base de datos de SSO. ENTSSO MA es un *exportación basados en llamada* solo agente de administración.  
  
 Configure el agente de administración en tres partes independientes:  
  
- Un archivo de configuración (ENTSSO.xml)  
  
- La interfaz de usuario de MIIS  
  
- La interfaz de usuario de ENTSSO  
  
  Los temas de esta sección describen el proceso de configuración.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configuración del archivo XML](../core/configuring-the-xml-file.md)  
  
-   [Cómo configurar MIIS para ENTSSO MA](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [Cómo configurar ENTSSO para la sincronización de contraseñas MIIS](../core/how-to-configure-entsso-for-miis-password-sync.md)