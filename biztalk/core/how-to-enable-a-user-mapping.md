---
title: Cómo habilitar una asignación de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enabling, user maps [SSO]
- maps [SSO], enabling
- managing [SSO maps], enabling
ms.assetid: 0f6448c9-944e-45f6-9436-87a4f3743498
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfd87d300314616fe05a033360d84f5d2eb8b8cd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970834"
---
# <a name="how-to-enable-a-user-mapping"></a>Cómo habilitar una asignación de usuario
Es necesario habilitar una asignación de usuarios antes de que se pueda utilizar la asignación en el sistema de inicio de sesión único.  
  
 Cuando se habilita una asignación de usuarios, aparecerá como (E)  **\<dominio\>\\< nombre de usuario\>**  al enumerar las asignaciones de usuario.  
  
 Tenga en cuenta que, si se han establecido credenciales utilizando el comando -setcredentials, la asignación ya se habrá habilitado.  
  
### <a name="to-enable-a-user-mapping-using-the-administration-utility"></a>Para habilitar una asignación de usuarios con la utilidad de administración  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage-enablemapping \<dominio\>\\< nombre de usuario\>\<nombre de la aplicación\>**, donde  **\< dominio\>**  es el dominio de Windows para la cuenta de usuario  **\<nombre de usuario\>**  es el nombre de usuario de Windows para el que desea habilitar las credenciales y  **\<nombre de la aplicación\>**  es el nombre de la aplicación afiliada que desea quitar la asignación de usuario y, a continuación, presione ENTRAR.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-enable-a-user-mapping-using-the-client-utility"></a>Para habilitar una asignación de usuarios con la utilidad de cliente  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssoclient – enablemapping \<nombre de la aplicación\>**, donde  **\<nombre de la aplicación\>**  es el nombre de la aplicación afiliada que desee Para quitar la asignación de usuario.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear asignaciones de usuario](../core/how-to-create-user-mappings.md)   
 [Asignaciones de SSO](../core/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)   
 [Administración de asignaciones de usuarios](../core/managing-user-mappings.md)