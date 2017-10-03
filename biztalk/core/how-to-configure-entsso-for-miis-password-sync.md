---
title: "Cómo configurar ENTSSO para la sincronización de contraseña MIIS | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89438935-37c1-4ac9-9ca2-7af8d9bfd3ae
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a1587c2e3c0d2164a7ffd3842b3d74df5b04685
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-entsso-for-miis-password-sync"></a>Cómo configurar ENTSSO para la sincronización de contraseñas de MIIS
Después de configurar el archivo XML y Microsoft Identity Integration Server (MIIS), el resto de los pasos de configuración deben llevarse a cabo en el sistema de Inicio de sesión único empresarial (ENTSSO).  
  
### <a name="to-allow-password-sync-from-miis"></a>Para permitir la sincronización de contraseñas desde MIIS  
  
1.  En Enterprise Single Sign-On, haga clic en el **servidores** nodo.  
  
2.  Haga clic en el servidor adecuado y haga clic en **propiedades**.  
  
3.  Haga clic en el **la sincronización de contraseñas** ficha.  
  
4.  Seleccione **Permitir sincronización de contraseñas desde MIIS**.  
  
5.  Haga clic en **Aceptar**.  
  
### <a name="to-enable-password-sync-on-the-system-level"></a>Para habilitar la sincronización de contraseñas en el sistema  
  
1.  En Enterprise Single Sign-On, haga clic en el **System** nodo.  
  
2.  Haga clic en **Propiedades**.  
  
     El **propiedades** aparece el cuadro de diálogo.  
  
3.  Haga clic en el **opciones** ficha.  
  
4.  En el **Habilitar sincronización de contraseñas** campo, seleccione **de Windows con los adaptadores de**.  
  
     **Configuración adicional**  
  
     Por último, debe configurar uno de los siguientes elementos:  
  
    -   Un Adaptador de sincronización de contraseñas que acepte la Sincronización de contraseñas de Windows.  
  
    -   La Sincronización directa de contraseñas debe estar habilitada en al menos una aplicación.  
  
     Para obtener más información sobre cómo llevar a cabo este procedimiento, consulte la documentación de sincronización de contraseñas.  
  
### <a name="to-configure-the-entsso-ma-for-miis-password-sync"></a>Para configurar ENTSSO MA para la sincronización de contraseñas de MIIS  
  
1.  En el agente de administración de ENTSSO **propiedades** página, haga clic en **configurar extensiones**.  
  
2.  En el **información de conexión para la extensión de la contraseña** , a continuación, haga clic en **configuración**.  
  
3.  En el **conectar a** campo escriba el nombre del equipo que va a recibir los cambios de contraseña.  
  
     El nombre del equipo debe tener el mismo formato que el que se utilizó en la creación del Nombre principal del servicio (SPN) del servicio ENTSSO del dominio.  
  
     Por ejemplo:  
  
     Formato corto - SPN = ENTSSO/ABCD1411, escriba ABCD1411  
  
4.  Formato largo - SPN = ENTSSO/ABCD1411.CompanyName.com, escriba ABCD1411.CompanyName.com  
  
### <a name="additional-configuration-steps"></a>Pasos de configuración adicional  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Identity Integration Server**y, a continuación, haga clic en **Identity Manager**.  
  
2.  En el menú **Herramientas** , haga clic en **Opciones**.  
  
3.  Seleccione **habilitar la sincronización de contraseña**.  
  
4.  En el **Ver agentes de administración**, seleccione **ADMA**.  
  
5.  En el **acción** panel, seleccione **propiedades**.  
  
6.  En el **propiedades** página, seleccione **configurar particiones de directorio**y, a continuación, seleccione **habilitar esta partición como un origen de sincronización de contraseña**.  
  
7.  Haga clic en **destinos**y, a continuación, seleccione ENTSSOMA2 para que pueda recibir cambios de contraseñas desde MIIS. Anule la selección de ENTSSOMA. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
8.  En el **Management Agent** visualizarla, seleccione **ENTSSOMA2**. En el panel derecho, seleccione **propiedades**. En el **propiedades** página, haga clic en **configurar extensiones**.  
  
9. Confirme que **habilitar la administración de contraseñas** está seleccionada y, a continuación, haga clic en **configuración**.  
  
10. En el **configuración de conexión** cuadro de diálogo, especifique lo siguiente:  
  
    -   Conectarse a: INTSVR1.fabrikam.com  
  
    -   Usuario: fabrikam\ssosvcact  
  
    -   Contraseña: ssosvcact  
  
        > [!NOTE]
        >  Los datos de esta cuenta deben coincidir con la cuenta del servicio ENTSSO configurada en INTSVR1.fabrikam.com.  
  
11. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
12. También se puede deshabilitar la sincronización de contraseñas para MIIS. Para ello, en **Identity Manager**, haga clic en el **herramientas** menú, haga clic en **opciones**y, a continuación, anule la selección **Enable Password Synchronization**.  
  
     Sin embargo, se aplicarán las siguientes restricciones:  
  
    -   Para que la sincronización de contraseñas funcione correctamente, el SPN debe configurarse en la cuenta de servicio de ENTSSO con la que el agente de administración de ENTSSO se vaya a comunicar.  
  
    -   La comunicación entre MIIS y el servidor de ENTSSO requiere Kerberos.  
  
13. Cuando configure la extensión de contraseña en la configuración de la conexión de MIIS para el agente de administración de ENTSSO, la cuenta especificada deberá coinicidir con la cuenta de servicio del servidor de ENTSSO que reciba las contraseñas de MIIS.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar al agente de administración de ENTSSO](../core/how-to-use-the-entsso-management-agent.md)