---
title: Cómo configurar MIIS para ENTSSO MA | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7820384-ff64-4628-9e35-02b13803928f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 969a52beb02c3d2ba237369c16efec9ee84e2ef1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248140"
---
# <a name="how-to-configure-miis-for-entsso-ma"></a>Cómo configurar MIIS para el agente de administración de ENTSSO
Al instalar la característica de administración de inicio de sesión único (SSO) empresarial (ya sea la versión completa o la de administración) en un equipo que ejecute Microsoft Identity Integration Server (MIIS), el agente de administración de ENTSSO se instala de forma automática. Esto implica que, al abrir MIIS, ya se han establecido casi todos los parámetros de configuración. La única parte que falta es la información de conexión.  
  
 Antes de comenzar el procedimiento, asegúrese de que la siguiente información está disponible:  
  
-   Nombre del servidor de ENTSSO.  
  
-   El Id. de usuario y la contraseña de la cuenta de Windows que utilizará el agente de administración de ENTSSO para comunicarse con el servidor de SSO.  
  
### <a name="to-configure-the-management-agent-within-miis"></a>Para configurar el agente de administración en MIIS  
  
1.  Abra MIIS y el **Identity Manager**.  
  
2.  Abra la **crear agente de administración** cuadro de diálogo.  
  
3.  Seleccione **Enterprise Single Sign-On** en la lista.  
  
     Esto inicia el **Asistente para crear un agente de administración**.  
  
4.  En el **configurar la información de conexión** página, en la **Connect To:** , escriba el nombre del servidor de SSO.  
  
5.  Escriba el nombre del agente de administración de ENTSSO. Debe coincidir con el nombre especificado en el archivo ENTSSO.xml.  
  
6.  En el **usuario** campo, especifique la cuenta de dominio que utiliza el agente de administración de ENTSSO para administrar las asignaciones en la base de datos de SSO.  
  
     La cuenta debe ser miembro de las cuentas de administradores de SSO o de las de administradores afiliados de SSO en el sistema de inicio de sesión único.  
  
7.  En el **contraseña** , escriba la contraseña para ese usuario.  
  
8.  Haga clic en **siguiente**, acepte los valores predeterminados hasta llegar a la **configurar extensiones** página.  
  
9. Cerca de **información de conexión** para la extensión de contraseña, haga clic en **configuración**.  
  
     El **configuración de conexión** aparece el cuadro de diálogo.  
  
10. En el **Connect To** cuadro, escriba la cuenta correspondiente. Esta cuenta debe coincidir con la cuenta de servicio del servicio de ENTSSO que se ejecuta en el equipo especificado.  
  
11. En el **usuario** y **contraseña** campos, escriba el nombre de usuario y la contraseña de la cuenta.  
  
12. Haga clic en **Aceptar**.  
  
13. En el **MIISCreate Management Agent**, haga clic en **finalizar**.  
  
14. Mientras sigue en la **Identity Manager**, haga clic en el **herramientas** menú y, a continuación, haga clic en **opciones**.  
  
     El **opciones** aparece el cuadro de diálogo.  
  
15. Seleccione **habilitar la extensión de las reglas del metaverso**.  
  
16. En el **campo de nombre de extensión de reglas**, escriba **Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**.  
  
17. Haga clic en **Aceptar** y cierre MIIS.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar al agente de administración de ENTSSO](../core/how-to-use-the-entsso-management-agent.md)