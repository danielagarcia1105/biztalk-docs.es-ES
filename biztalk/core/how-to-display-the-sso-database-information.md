---
title: Cómo mostrar la información de la base de datos SSO | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], viewing SSO database
- SSO database, viewing
- viewing, SSO database
ms.assetid: 0ebadd2e-6ea5-460c-b0a8-f48589e6bf1c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e834874cb87da598db0bc92e516b58dfe2da9069
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969330"
---
# <a name="how-to-display-the-sso-database-information"></a>Cómo mostrar la información de la base de datos SSO
Es posible ver la información de la base de datos de SSO utilizando el Complemento MMC o la utilidad de línea de comandos (ssomanage).  
  
### <a name="to-display-the-sso-database-information-using-the-mmc-snap-in"></a>Para mostrar la información de la base de datos de SSO utilizando el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **System**y, a continuación, haga clic en **propiedades**.  
  
4.  Haga clic en las pestañas en el **propiedades del sistema** cuadro de diálogo para ver la información de la base de datos SSO.  
  
### <a name="to-display-the-sso-database-information-using-the-command-line"></a>Para mostrar la información de la base de datos de SSO utilizando la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage – displaydb**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-display-the-sso-database-the-sso-server-is-connected-to-using-the-command-line"></a>Para mostrar la información de la base de datos de SSO, la conexión con el servidor de SSO se efectúa mediante la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage – showdb**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
 En la siguiente tabla se describen los valores que estos procedimientos muestran.  
  
|Propiedad|Valor|  
|--------------|-----------|  
|SQL Server|**\<Nombre de SQL Server\>**|  
|Single Sign-On base de datos|**\<Nombre de la base de datos de SQL Server\>**|  
|Nombre del servidor secreto de inicio de sesión único|**\<Nombre del servidor de inicio de sesión único\>**|  
|Cuenta de administradores de inicio de sesión único|Dominio\nombre de cuenta|  
|Cuenta de administradores afiliados de inicio de sesión único|Dominio\nombre de cuenta|  
|Tamaño de la tabla de auditoría para las aplicaciones eliminadas (número de entradas de auditoría)|1.000 (valor predeterminado)|  
|Tamaño de la tabla de auditoría para las asignaciones de usuario eliminadas (número de entradas de auditoría)|1.000 (valor predeterminado)|  
|Tamaño de la tabla de auditoría para búsquedas de credenciales externas (número de entradas de auditoría)|1.000 (valor predeterminado)|  
|Tiempo de espera de vales (en minutos)|2 (valor predeterminado)<br /><br /> Este valor puede ser un entero comprendido entre 1 y 525.600|  
|Tiempo de espera de caché de credenciales (en minutos)|60 (valor predeterminado)|  
|Estado de inicio de sesión único|Habilitado o deshabilitado|  
|Vales permitidos|Sí o no (predeterminado)|  
|Validar vales|Sí (predeterminado) o no|  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar los vales de SSO](../core/how-to-configure-the-sso-tickets.md)   
 [Uso de SSO](../core/using-sso.md)