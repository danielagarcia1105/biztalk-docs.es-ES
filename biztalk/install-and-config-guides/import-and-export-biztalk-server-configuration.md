---
title: Importar y exportar la configuración de BizTalk Server | Microsoft Docs
description: Pasos para aplicar, importar, exportar o quitar la configuración de los componentes y actualizar las bases de datos y las cuentas de servicio de BizTalk Server
ms.custom: ''
ms.date: 08/14/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6206ed8-d087-44cc-8ab5-da5d8a28e09a
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60faef2bf700a5e7fa1f5ced556e9fdd572201b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980741"
---
# <a name="import-and-export-biztalk-server-configuration"></a>Importar y exportar la configuración de BizTalk Server
La configuración de BizTalk Server proporciona un análisis de alto nivel del estado de configuración de las características instaladas en el equipo local. La herramienta permite configurar las funciones y quitar su configuración, definir la configuración de seguridad, así como importar configuraciones y exportarlas.  
  
## <a name="prerequisites-to-use-the-biztalk-server-configuration"></a>Requisitos previos para usar la configuración de BizTalk Server  
   
-   La cuenta que ha iniciado sesión como debe ser miembro del grupo local Administradores y tener derechos de administrador del sistema en SQL Server.  
  
-   Las cuentas predeterminadas que genera BizTalk Server y que se enumeran en la configuración de BizTalk Server son grupos locales. En un entorno multiservidor, reemplace estos grupos locales con grupos de dominio.  
  
-   La cuenta que ha iniciado sesión como debe ser miembro del grupo Administradores de OLAP en el equipo OLAP, si la configuración.  
  
    > [!NOTE]
    >  Si cambia la pertenencia a grupos del usuario con sesión iniciada actual y el grupo también es un miembro del dominio, estar seguro de cierre de sesión y vuelva a iniciar sesión una vez finalizados los cambios. Si no inicia sesión out/inicio de sesión en, se haya denegado acceso como nueva pertenencia a grupos no se refleja en el inicio de sesión actual.  
  
## <a name="apply-the-configuration"></a>Aplicar la configuración  
  
1.  En la **Configuración de BizTalk Server**, haga clic en **Aplicar configuración**.  
  
2.  En la pantalla **Resumen**, revise la configuración y, luego, haga clic en **Siguiente**.  
  
3.  En la pantalla **Finalización**, haga clic en **Finalizar**.  
  
## <a name="import-configuration"></a>Importar configuración

> [!IMPORTANT]
> Al importar un archivo de configuración, confirme que el archivo de configuración no configure un componente que no se ha instalado en el servidor BizTalk Server que está configurando. Al intentar configurar un componente inexistente en el servidor de BizTalk Server, puede producirse una condición de interbloqueo. En esta situación, desconfigurar los componentes que dependen del componente que intenta volver a configurar el archivo de configuración. Sin embargo, al intentar desconfigurar los componentes dependientes puede requerir que el componente que falta esté presente y configurado. Para resolver este problema, debe editar el archivo de configuración para quitar las referencias a componentes no instalados o aplicar el archivo de configuración para una instalación compatible de BizTalk Server.  
> 
>  No se guardan las contraseñas y las ubicaciones de archivo de copia de seguridad en el archivo de configuración que se va a importar, a menos que se haya editado manualmente el archivo. Si las características ya están configuradas, no se importan.  
  
  
1.  En la **Configuración de BizTalk Server**, haga clic en **Importar configuración**.  
  
2.  En el cuadro de diálogo **Abrir**, seleccione el archivo de configuración que quiera importar y, después, haga clic en **Abrir**.  
  
3.  En la **Configuración de BizTalk Server**, haga clic en **Aplicar configuración**.  
  
4.  En la pantalla **Resumen**, revise la configuración y, luego, haga clic en **Siguiente**.  
  
5.  En la pantalla **Finalización**, haga clic en **Finalizar**.  

Puede importar archivos de configuración de BizTalk Server mediante el marco de trabajo de configuración de BizTalk Server. Para obtener más información sobre cómo trabajar con estos archivos, consulte [Trabajo con Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md).  
  
## <a name="export-configuration"></a>Configuración de exportación

> [!NOTE]
>  Las contraseñas no se guardan en el archivo de configuración.    
 
1. En la **Configuración de BizTalk Server**, haga clic en **Exportar configuración**.  
  
2. En el cuadro de diálogo **Guardar como**, escriba el nombre del archivo que quiera guardar y, después, haga clic en **Guardar**.  

   Puede exportar las configuraciones de BizTalk Server mediante el marco de trabajo de configuración de BizTalk Server. Para obtener más información sobre cómo trabajar con estos archivos, consulte [trabajar con Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md)  
  
## <a name="unconfigure-features"></a>quitar la configuración de características;  
 Se puede quitar la configuración de las características de BizTalk Server del equipo al eliminarlas en la configuración de BizTalk Server.  
  
> [!NOTE]
>  Antes de desconfigurar las características, debe cerrarse la consola de administración de BizTalk Server.  
  
 
1.  En la **Configuración de BizTalk Server**, haga clic en **Quitar la configuración de características**.  
  
2.  En el cuadro de diálogo **Quitar la configuración de características**, seleccione las características que quiera quitar y, después, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Aparecerá un cuadro de diálogo que le advertirá de que está a punto de quitar la configuración de las características seleccionadas. Haga clic en **Sí** para continuar.  
  
3.  En la pantalla **Resumen**, revise la configuración y, luego, haga clic en **Siguiente**.  
  
4.  En la pantalla **Finalización**, haga clic en **Finalizar**.  
  
## <a name="update-databases"></a>Actualizar bases de datos  
 Se pueden cambiar las bases de datos y los servidores de bases de datos asociados con las características de BizTalk Server al editarlas en la configuración de BizTalk Server  
  
> [!NOTE]
>  Se admite la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con instancias predeterminadas e instancias con nombre de SQL Server.  
> 
>  Esta herramienta permite efectuar la edición masiva de las bases de datos.  
  
 
1.  En la **Configuración de BizTalk Server**, haga clic en **Ver** y, después, en **Bases de datos**.  
  
2.  En el cuadro de diálogo **Bases de datos**, seleccione la característica que quiera editar y, después, haga clic en **Editar**.  
  
3.  En el cuadro de diálogo **Bases de datos**, escriba el nombre del servidor de la base de datos y el nombre de la base de datos que quiera usar y, después, haga clic en **Aceptar**.  
  
4.  En el cuadro de diálogo **Bases de datos**, haga clic en **Cerrar**.  
  
## <a name="update-service-accounts"></a>Actualizar cuentas de servicio  
 Se pueden cambiar las cuentas de servicio asociadas con las características de BizTalk Server al editarlas en la configuración de BizTalk Server.  
  
> [!NOTE]
>  Esta herramienta permite efectuar la edición masiva de las cuentas.  
  
1.  En la **Configuración de BizTalk Server**, haga clic en **Ver** y, después, en **Cuentas de servicio**.  
  
2.  En el cuadro de diálogo **Cuentas de servicio**, seleccione la característica que quiera editar y, después, haga clic en **Editar**.  
  
3.  En el cuadro de diálogo **Credenciales de usuario**, escriba el nombre de usuario y la contraseña que quiera usar y, después, haga clic en **Aceptar**.  
  
4.  En el cuadro de diálogo **Cuentas de servicio**, haga clic en **Cerrar**.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)   
 [Trabajo con Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md)   