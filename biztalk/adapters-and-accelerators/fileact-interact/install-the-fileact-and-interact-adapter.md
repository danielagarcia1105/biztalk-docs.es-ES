---
title: Instalar el FileAct e InterAct adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf387d59-373b-4151-9dfd-30c511978862
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5ee288b9772b7585fe972a4335e3cf8c5595024
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989389"
---
# <a name="install-the-fileact-and-interact-adapter"></a>Instalar el FileAct e InterAct de adaptador
Esta sección proporciona instrucciones para instalar [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] para SWIFT. Antes de instalar a los adaptadores, debe instalar el software necesario.  
  
## <a name="prerequisites"></a>Requisitos previos  

* Inicie sesión con una cuenta que sea miembro del grupo Administradores local y un miembro del grupo Administradores de BizTalk Server
  
## <a name="step-1-install-biztalk-server-and-configure-bam"></a>Paso 1: Instalar BizTalk Server y configurar BAM

1. Instalar [BizTalk Server 2016](../../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md), o [BizTalk Server 2013 R2 / 2013](../../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md)e instalar la supervisión de la actividad económica (BAM).

2. Configurar [BizTalk Server](../../install-and-config-guides/configure-biztalk-server.md)y configurar la supervisión de la actividad económica (BAM).
  
3. Asegúrese de que tiene suficientes privilegios de seguridad para tener acceso a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. [Derechos de seguridad mínimos para BizTalk Server](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) es un excelente recurso.
  
## <a name="step-2-install-biztalk-accelerator-for-swift-a4swift"></a>Paso 2: Instalar el Acelerador de BizTalk para SWIFT (A4SWIFT)  

Instalar y configurar el [Acelerador de BizTalk para SWIFT](../../adapters-and-accelerators/accelerator-swift/install-configure-and-deploy-the-biztalk-accelerator-for-swift.md).

  
## <a name="step-3-install-swiftalliance-gateway-sag"></a>Paso 3: Instalar la puerta de enlace SWIFTAlliance (SAG)  
 Antes de instalar a los adaptadores FileAct e InterAct, cree el SAG socios de mensaje, puntos de conexión y reglas de enrutamiento y probar la conectividad SAG en el equipo donde instale los adaptadores FileAct e InterAct.

Consulte [ https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway ](https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway) obtener detalles específicos de la puerta de enlace SWIFTAlliance.  

## <a name="step-4-install-the-biztalk-fileact-and-interact-adapters"></a>Paso 4: Instalar a los adaptadores de BizTalk FileAct e InterAct  
  
1. Ejecute el **Setup.exe** como administrador para iniciar la instalación.  
  
2. Seleccione **Instalar**.  
  
3. Escriba el nombre de usuario y el nombre de la organización y, a continuación, seleccione **siguiente**.  
  
4. **Aceptar** el contrato de licencia.
  
5. En el **opciones de instalación** , realice una de las siguientes acciones:  
  
   - Seleccione el **completar** opción para instalar todos los componentes de la FileAct e InterAct de adaptadores.  
  
   - Seleccione el **personalizado** opción para elegir los componentes para instalar.  
  
     Compruebe la ubicación de instalación, o seleccione **examinar** para seleccionar una ubicación de instalación diferente. Seleccione **Siguiente**.  
  
6. En el **resumen** página, seleccione **instalar** para instalar los componentes de la lista.  
  
   > [!NOTE]
   >  Cuando **ejecutar el Asistente para configuración** está seleccionada (valor predeterminado), el **Microsoft BizTalk FileAct y configuración del adaptador interactúe** asistente se ejecuta automáticamente cuando se selecciona **finalizar**.  
  
7. Cuando se complete la instalación, seleccione **finalizar**. 

## <a name="next-steps"></a>Pasos siguientes

[Configurar el adaptador de FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/configure-the-fileact-and-interact-adapter.md)  
[Mensajes de ejemplo InterAct y FileAct](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md)  
[Desinstalar o reparar el adaptador de FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[Leer los problemas de instalación conocidos](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)
  
## <a name="see-also"></a>Vea también  
[Introducción a los adaptadores FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)  
[Descripción de la arquitectura de adaptador FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)