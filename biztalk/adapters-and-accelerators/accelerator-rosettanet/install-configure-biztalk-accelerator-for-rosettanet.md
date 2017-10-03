---
title: Instalar el Acelerador de BizTalk para RosettaNet (BTARN) en BizTalk Server | Documentos de Microsoft
description: "Consulte los requisitos de hardware y software, los pasos de instalación y los pasos de configuración de BTARN en BizTalk Server"
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a40eca3ccd2092cc3024e0ad69d3737bad869180
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-biztalk-accelerator-for-rosettanet"></a>Instalar el Acelerador de BizTalk para RosettaNet

## <a name="overview"></a>Información general
Instalar el Acelerador de Microsoft BizTalk para RosettaNet (BTARN).
  
> [!NOTE]
>  En la edición Enterprise de BizTalk Server, puede instalar solo la Enterprise Edition de Acelerador de BizTalk para RosettaNet (BTARN). En el servidor Standard Edition de BizTalk, puede instalar solo la Standard Edition de Acelerador de BizTalk para RosettaNet (BTARN).  
  
 La instalación de BTARN incluye lo siguiente:  
  
-   Administración de BTARN  
  
-   Programaciones XLANG del Diseñador de orquestaciones de BizTalk [modelos PIP (Proceso de interfaz de socio)]  
  
-   Marco de implementación de RosettaNet (RNIF)  
  
-   Base de datos BTARN  
  
-   Aplicaciones web del front-end HTTP  
  
## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y de software

Los requisitos mínimos de hardware y software son el mismo que el servidor BizTalk Server.

|  |Requisitos de BizTalk  |Requisitos de SQL y el sistema operativo |  
|---------|---------|--------- | 
| [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [Hardware and Software Requirements for BizTalk Server 2016](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016) | **Requisitos de hardware y software de SQL Server**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Requisitos de hardware de Windows Server**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx) |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> BizTalk Server 2013 | [Requisitos de hardware y Software para BizTalk Server 2013 y 2013 R2](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) |**Requisitos de hardware y software de SQL Server**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Requisitos de hardware de Windows Server**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx)  |

> [!TIP] 
> Los requisitos de hardware enumerados son los mínimos. Cada entorno es diferente y es muy probable que el suyo tenga más requisitos. Consulte [Recommendations for Installing, Sizing, Deploying, and Maintaining a BizTalk Server Solution](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx) (Recomendaciones para instalar, ajustar el tamaño, implementar y mantener una solución de BizTalk Server). 

## <a name="install-and-configure"></a>Instalar y configurar

### <a name="before-you-begin"></a>Antes de empezar

* Para la base de datos BTARN, BTARN solo configura las propiedades de nombre de base de datos y el nombre de equipo de SQL Server. Información acerca de estas propiedades se almacena en el registro.
* Inicie sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. 
* En la descarga de BizTalk Server, el programa de instalación BTARN está en el `\BizTalk Accelerators` carpeta.
* BizTalk Server debe estar instalado y debe estar ejecutando SQL Server.
* BTARN y BizTalk Server requieren Microsoft .NET Framework como requisito previo de software. Si tiene varias versiones de .NET Framework instalada en el equipo, asegúrese de que se hace referencia a la aplicación BtarnAPP Web clásico de .NET Framework 4.0. Esto se puede configurar mediante el Administrador de Internet Information Services (IIS).  
* La cuenta de instancias de host de BizTalk y la cuenta de instancias de hosts aislados de BizTalk deben ser la misma. En caso contrario, BTARN no funcionará correctamente.  
* BTARN le permite agregar únicamente cuentas de servicio individuales y no los grupos, en el grupo de administradores de BizTalk Server o el grupo de usuarios de la aplicación de BizTalk.  
* Deberá crear una extensión de servicio web para BTSHTTPReceive.dll, configurando el modo de aislamiento de IIS. Para obtener más información, vea la entrada "404 no encontrado errores al enviar una solicitud HTTP" en el tema "Solución de problemas: problemas y soluciones" en [http://go.microsoft.com/fwlink/?LinkId=188560](http://go.microsoft.com/fwlink/?LinkId=188560). Consulte también [cómo configurar IIS para una ubicación de recepción HTTP](../../core/how-to-configure-iis-for-an-http-receive-location.md).  
* Agregue el servidor (http:// <*nombre del servidor*>) a la zona Internet Local en las opciones de seguridad de Internet Explorer.  
*  Si se usa una instancia remota de SQL mediante el puerto no predeterminado para configurar BTARN, las herramientas de cliente de SQL Server deberán instalarse a nivel local. Para obtener más información, consulte [Guía de instalación de BizTalk Server para entornos de varios equipos](../../install-and-config-guides/install-biztalk-server-in-a-multi-computer-environment.md).
*  Debe usarse un grupo independiente para el rol: el Administrador de BizTalk, los usuarios de Host de BizTalk y usuarios de hosts aislados de BizTalk durante la configuración de BizTalk Server.  
*  BTARN no admite el uso de alias creados para que la instancia de SQL para configurar la base de datos BTARN.  

### <a name="install-btarn"></a>Instalar BTARN

1.  Ejecute el BTARN **setup.exe** como administrador.
  
2.  Seleccione **Instalar**.  
  
3.  En el **información del cliente** página, escriba su nombre de usuario, su organización y la clave de producto y, a continuación, haga clic en **siguiente**.  
  
4.  En el **contrato de licencia** página, lea el contrato de licencia de usuario final y, a continuación, haga clic en **Accept**.  
  
    > [!NOTE]
    >  Si no acepta el contrato de licencia, no puede continuar con la instalación.  
  
5.  En el **opciones de instalación** página, seleccione **completar** para una instalación completa o **personalizado** para una instalación parcial. Asegúrese de que la ruta de instalación es correcta y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Si selecciona **personalizado**, seleccione los componentes para instalar desde el **instalación personalizada** página. Si opta por instalar componentes de SDK o la documentación, debe tener instalado antes de ejecutar el programa de instalación de .NET Framework.  
  
6.  En el **resumen** página, revise los componentes que está instalando y, a continuación, haga clic en **instalar**. El **progreso de la instalación** pantalla muestra el progreso del procedimiento de instalación.  
  
7.  En el **instaló** página, asegúrese del **ejecutar el Asistente para configuración** casilla está seleccionada y, a continuación, haga clic en **finalizar**.  
  
     Se abre el Asistente para configuración de BTARN. A continuación, configure BTARN.  
  
    > [!IMPORTANT]
    >  Si realiza una instalación personalizada para instalar sólo la característica Front-End de HTTP de BTARN, la configuración de BTARN puede producir un error después de que el programa de instalación se completa, mostrar el "no se pudo crear el objeto para la característica: aplicación Web" error. Si esto ocurre, copie los dos archivos (**Microsoft.VC80.ATL.manifest** y **atl80.dll**) desde un equipo con BizTalk Server instalado en él, en el equipo donde haya instalado la característica Front-End de HTTP de BTARN.  
    >   
    >  Si Visual Studio está instalado en el mismo equipo que BizTalk Server, la carpeta de origen de los dos archivos es *< unidad\>*: \Program Visual Studio 11.0\VC\redist\x86\Microsoft.VC100.ATL. Si Visual Studio no está instalado en el servidor BizTalk server, la carpeta de origen de los dos archivos en el servidor de BizTalk es una carpeta bajo *< unidad\>*: \WINDOWS\WinSxS. La versión de los archivos debe ser 8.0.50727.42. La carpeta de destino en el equipo donde ha instalado la característica Front-End HTTP es el directorio de instalación de BTARN (de forma predeterminada, *< unidad\>*: \Program BTARN).  
    >   
    >  Una vez copiados estos archivos en el equipo con la característica de Front-End HTTP instalada, vuelva a ejecutar **Configuration.exe**.  
  
### <a name="configure-btarn"></a>Configurar BTARN  

> [!TIP]
 >  Antes de configurar BTARN, asegúrese de que asignar .NET Framework en asignaciones de controlador en IIS. Además, al configurar BTARN, debe crear manualmente el grupo IIS_WPG.  
   
1.  En el **Asistente de configuración de Microsoft BTARN** página, seleccione **configuración básica** para configurar el servidor con la configuración predeterminada, o **configuración personalizada** a configurar el servidor mediante las opciones de configuración avanzada.  
  
    > [!NOTE]
    >  Si desea configurar BTARN usando una cuenta de administrador local, escriba la cuenta como *< nombre de la máquina\>\\< nombre de administrador\>*  en el **Id. de usuario** campo de la **Service Credential** área.  
  
2.  En el **el nombre del servidor de base de datos** texto cuadro, compruebe que el nombre del servidor muestra es correcto. En el **credencial del servicio** área, escriba el nombre de usuario (con el dominio) y la contraseña de la cuenta que se ejecutarán los servicios. Haga clic en **configurar**.  
  
3.  Si la cuenta tiene privilegios administrativos, haga clic en **Sí** para continuar con la configuración.  
  
4.  Si seleccionó **configuración básica** en el paso 1, compruebe la lista de componentes que se pueden configurar en el **resumen** cuadro de diálogo y, a continuación, haga clic en **siguiente**. Vaya al paso 10.  
  
5.  Si seleccionó **configuración personalizada** en el paso 1, siga estos pasos:  
  
    > [!NOTE]
    >  La configuración de BTARN da error si usa caracteres especiales en el nombre de alguna de las bases de datos de BTARN.  
  
6.  Para configurar el tiempo de ejecución, en la **configuración de Microsoft BTRAN** cuadro de diálogo, haga clic en **en tiempo de ejecución** en el panel izquierdo. A la derecha **en tiempo de ejecución** panel, haga clic en **habilitar la característica de tiempo de ejecución en este equipo**. Para unirse a un grupo de base de datos existente, desactive **¿desea crear un nuevo grupo de base de datos**. Seleccione el nombre de servidor web, el número de puerto, los almacenes de datos, la cuenta de servicio del grupo de aplicaciones y la carpeta virtual de recepción HTTP de BizTalk.  
  
7.  Para configurar la característica de aplicaciones Web, en la **configuración de Microsoft BTRAN** cuadro de diálogo, haga clic en **móviles** en el panel izquierdo y, a continuación, haga clic en **habilitar la característica de tiempo de ejecución en este equipo**. Escriba el nombre de servidor BizTalk Server adecuado y número de puerto o seleccionar los valores predeterminados. Seleccione la carpeta virtual de aplicación web que corresponda.  
  
8.  Haga clic en **Aplicar configuración**.  
  
9. En el **resumen** página, haga clic en **siguiente**.  
  
10. En el **completar la configuración** página, haga clic en **finalizar**.  
  
    > [!NOTE]
    >  Después de instalar BTARN, el administrador del sistema debe agregar usuarios a los grupos Usuarios empresariales, Gestores empresariales y Administradores empresariales. Si es administrador del sistema, debe rellenar estos grupos, cerrar sesión y volver a iniciar sesión después de haberse agregado usted mismo a los grupos.
  
    > [!WARNING]
    >  Deben usarse tres grupos diferentes al configurar BizTalk Server para el Administrador de BizTalk, los usuarios de Host de BizTalk y usuarios de hosts aislados de BizTalk.  

## <a name="start-the-artifacts"></a>Iniciar los artefactos
Las orquestaciones de BTARN, puertos de envío y ubicaciones de recepción no se inician automáticamente después de configurar BTARN.
  
> [!NOTE]
>  Inicie los puertos de envío PrivateInitiator_To_LOB y PrivateResponder_To_LOB para poder iniciar las orquestaciones PrivateInitiatorProcess y PrivateResponderProcess.  
  
-   En los equipos en los que haya configurado un servidor virtual de Internet Information Services (IIS) con Capa de sockets seguros (SSL), debe configurar el servidor virtual para que acepte el certificado cliente. Vea [paso 4: habilitar SSL en IIS](step-4-enabling-secure-sockets-layer-in-iis.md) en el [doble acción Tutorial](double-action-tutorial.md).
  
 
1.  Abra **administración de BizTalk Server** como administrador.  
  
2.  Expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **BizTalk Application 1**.  
  
3.  Haga clic en **puertos de envío**. En el panel derecho, para cada puerto de envío que no se ha iniciado, haga clic en y, a continuación, haga clic en **iniciar**.  
  
4.  Haga clic en **puertos de recepción** y **ubicaciones de recepción**. En el panel derecho, haga clic en y, a continuación, haga clic en para cada ubicación de recepción que no se ha iniciado, **iniciar**.  
  
    > [!NOTE]
    >  Debe iniciar los puertos de envío PrivateInitiator_To_LOB y PrivateResponder_To_LOB para poder iniciar las orquestaciones PrivateInitiatorProcess y PrivateResponderProcess.  
  
5.  Haga clic en **orquestaciones** y **ubicaciones de recepción**. En el panel derecho, para cada orquestación que no se ha iniciado, haga clic en y, a continuación, haga clic en **iniciar**.  
  
## <a name="restart-your-computer"></a>Reinicie el equipo  
  
Reinicie el equipo para aplicar las modificaciones que ha realizado en la configuración y los permisos.  
  
> [!NOTE]
>  Los desarrolladores pueden optar por instalar y configurar BTARN en un solo servidor con fines de desarrollo, copias de ensayo o pruebas. Utilizan este servidor para escribir su propio código personalizado y probarlo antes de pasarlo a producción.  
  
 Para obtener más información sobre la instalación de BTARN en un único servidor, consulte el [Tutorial de bucle invertido](loopback-tutorial.md).
  
## <a name="next-steps"></a>Pasos siguientes  
  
* [Actualización del Acelerador para RosettaNet](upgrade-biztalk-accelerator-for-rosettanet.md)
* [Desinstale el Acelerador para RosettaNet](uninstall-biztalk-accelerator-for-rosettanet.md)
* [Solucionar problemas de la instalación y consulte los problemas de instalación conocidos](troubleshoot-known-issues-installation.md)