---
title: Instalar BizTalk Server 2016 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f5ac913-0734-45b2-8e25-1db146d81858
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f89aa7599040a2cc6c50f11b70c2751fcf2df1ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-biztalk-server-2016"></a>Instalar BizTalk Server 2016
Instale BizTalk Server en un solo equipo.

## <a name="before-you-get-started"></a>Antes de comenzar

* **Administrador del sistema**: cuando se instala SQL Server, el programa de instalación concede automáticamente derechos de administrador del sistema a la cuenta con la que se ha iniciado sesión. Puesto que estos derechos también son necesarios para instalar BizTalk Server, realice alguna de las siguientes acciones:
  * Use la misma cuenta que usó al instalar SQL Server.
  * Conceda derechos de administrador del sistema a la cuenta con la que se ha iniciado sesión.
  * Confirme que la cuenta con la que se ha iniciado sesión pertenece al grupo de administradores locales.
* **Nombres de cuenta**: use los nombres de cuenta predeterminados siempre que sea posible. El programa de instalación de BizTalk Server especifica de forma automática las cuentas predeterminadas. Si hay varios grupos de BizTalk Server en el dominio, cambie los nombres de cuenta para evitar conflictos. Si cambia los nombres, BizTalk Server solo admite el formato *Nombre de dominio de NetBIOS\usuario* para cuentas de servicio y grupos de Windows.
* **Nombres de cuenta con Servicio web de administración de BAM**: BizTalk Server no admite el uso de cuentas integradas o cuentas sin contraseña para el usuario del Servicio web de administración de BAM. El servicio web accede a la base de datos de BizTalk Server y estas cuentas pueden suponer una amenaza para la seguridad.

    > [!NOTE] 
    > La configuración de BizTalk Server con estos tipos de cuenta puede funcionar, pero se produce un error con el Servicio web de administración de BAM. Se pueden usar cuentas integradas o cuentas sin contraseña para el grupo de aplicaciones de BAM.

* **Visor de ensamblados de BizTalk**: no se admite en una plataforma de 64 bits. 
* **Instalar y desinstalar**: para desinstalar BizTalk Server, debe eliminar manualmente las bases de datos de BizTalk Server. Si instala BizTalk Server como desarrollador o evaluador, use una máquina virtual. Si tiene que reinstalarlo, puede revertir fácilmente la máquina virtual sin tener que desinstalar ni eliminar las bases de datos.
* **Equipos de 32 y 64 bits**: hay algunas diferencias cuando se instala BizTalk Server en un equipo de 32 o de 64 bits. El proceso de instalación y configuración cubre equipos de 32 y 64 bits. Las posibles diferencias se indican.
* **Grupos de trabajo**: se admiten la instalación y la configuración de BizTalk Server en el entorno de grupo de trabajo de un único equipo. Las características y componentes de SQL Server y BizTalk Server se instalan y configuran en el mismo equipo.


## <a name="install-biztalk-server"></a>Instalar BizTalk Server
1. Cierre todos los programas abiertos. Ejecute el programa de instalación de BizTalk Server como administrador.
2. Seleccione **Instalar Microsoft BizTalk Server 2016**.
3. Escriba el **Nombre de usuario**, la **Organización** y la clave de producto. Seleccione **Siguiente**.
4. Acepte el contrato de licencia y seleccione **Siguiente**.
5. Elija participar en el Programa para la mejora de la experiencia del usuario y seleccione **Siguiente**.
6. Elegir los componentes que quiere instalar:

    ![bts2016install_components](../install-and-config-guides/media/bts2016install-components.gif)
  
    Asegúrese de seleccionar **Software adicional**. También puede cambiar la ubicación de instalación: 
  
    ![bts2016install_additional](../install-and-config-guides/media/bts2016install-additional.gif)

    Seleccione **Siguiente**.   
  
 7. En función de los componentes que elija, puede haber algunos requisitos previos adicionales, como ADOMD.NET. El programa de instalación puede instalar automáticamente todos los requisitos previos redistribuibles. Existen varias opciones:
* **Instalar manualmente los requisitos previos redistribuibles**: el Asistente para instalación se cierra para que pueda instalar manualmente los requisitos previos que faltan.
* **Instalar automáticamente los requisitos previos redistribuibles desde Internet**: valor predeterminado. Esta opción requiere acceso a Internet.
* **Descargar el archivo .cab de requisitos previos redistribuibles**: descarga un archivo CAB, que puede instalar más adelante.
* **Instalar automáticamente los requisitos previos redistribuibles desde un archivo .cab**: si ya ha descargado los archivos CAB, puede seleccionar esta opción para usarlos. 

  Seleccione **Siguiente**.
  
8. Revise la página de resumen. Para realizar algún cambio, seleccione **Atrás**. De este modo, puede activar o desactivar componentes. 

     Para habilitar el inicio de sesión automático después de reiniciar el sistema, seleccione **Establecer** y especifique la cuenta de inicio de sesión. Esto solo se habilita durante la instalación de BizTalk. Cuando finalice la instalación, esta configuración se deshabilita. 

    Elija **Instalar**.
  
9. Para configurar ahora BizTalk, active la opción **Iniciar configuración de BizTalk Server**. Si no quiere configurar ahora BizTalk, desactive esta opción y seleccione **Finalizar** para cerrar el Asistente para instalación. 

Se genera un archivo de registro de instalación en una carpeta temporal, similar al siguiente: `C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm`.
  
## <a name="check-the-installation"></a>Comprobar la instalación

* BizTalk Server aparece en **Programas y características**.
* En la clave del Registro `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0` se muestra la versión de BizTalk Server, la ruta de instalación, la edición y otros detalles.
* En sus aplicaciones se muestran la administración de BizTalk Server, la configuración y otros componentes. 

## <a name="next-step"></a>Paso siguiente
[Configuración de BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)