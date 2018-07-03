---
title: Cómo auditar SSO | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], auditing
- SSO, auditing
- auditing [SSO]
- SSO database, auditing
ms.assetid: dc6d0726-fc31-4af2-9a23-8df9e3fc5836
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9363df166e438aba0db89cbadd0d688c7d353a0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972085"
---
# <a name="how-to-audit-sso"></a>Cómo auditar el inicio de sesión único
Puede utilizar el Complemento MMC o la línea de comandos para establecer los niveles de auditoría positivo y negativo. Los resultados de la auditoría se almacenan tanto en los registros de sucesos como en los de auditoría de la base de datos.  
  
 Los administradores de SSO pueden establecer niveles de auditoría positivos y negativos que se ajusten a sus directivas corporativas. Puede establecer auditorías positivas y negativas en uno de los niveles siguientes:  
  
 0 = Ninguno  
  
 1 = Bajo  
  
 2 = Medio  
  
 3 = Alto. Este nivel ejecuta todos los mensajes de auditoría posibles.  
  
 El valor predeterminado para la auditoría positiva es 0 (ninguno) y para la auditoría negativa, 1 (bajo).  
  
 Para modificar la auditoría del nivel de base de datos, debe actualizar la base de datos de SSO mediante un archivo XML. Un ejemplo de archivo XML para actualizar la base de datos de SSO es:  
  
```  
<sso>  
<globalnfo>  
<auditDeletedApps>1000</auditDeletedApps>  
<auditDeletedMappings>1000</auditDeletedMappings>  
<auditCredentialLookups>1000</auditCredentialLookups>  
</globalInfo>  
</sso>  
  
```  
  
### <a name="to-audit-single-sign-on-using-the-mmc-snap-in"></a>Para auditar el inicio de sesión único con el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **sistema**y, a continuación, haga clic en **propiedades**.  
  
4.  En el **las propiedades del sistema** cuadro de diálogo, haga clic en el **auditorías** ficha.  
  
5.  Especifique la configuración adecuada y haga clic en **Aceptar**.  
  
### <a name="to-audit-single-sign-on-using-the-command-line"></a>Para auditar el inicio de sesión único con la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo **ssoconfig-auditlevel \<positivo\>\<negativo\>**, donde **\<positivo\>** es el nivel de Cuando las acciones se realizan correctamente, la auditoría y **\<negativo\>** es el nivel de auditoría de las acciones no.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-audit-the-sso-database"></a>Para auditar la base de datos de SSO  
  
1. Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo **ssomanage – updatedb \<archivo de actualización\>**, donde  <strong>\<archivo de actualización\></strong>es la ruta de acceso y nombre del archivo.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo actualizar la base de datos SSO](../core/how-to-update-the-sso-database.md)   
 [Uso de SSO](../core/using-sso.md)