---
title: Instalar el FileAct e interactuar adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf387d59-373b-4151-9dfd-30c511978862
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48a3beccd6179bcb4526ba41f4f41a7923f5f966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-fileact-and-interact-adapter"></a>Instalar el FileAct e interactuar adaptador
Esta sección proporciona instrucciones para instalar [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] : para SWIFT. Antes de instalar a los adaptadores, debe instalar el software necesario.  
  
## <a name="prerequisites"></a>Requisitos previos  

* Inicie sesión con una cuenta que sea miembro del grupo Administradores local y un miembro del grupo Administradores de BizTalk Server
  
## <a name="step-1-install-biztalk-server-and-configure-bam"></a>Paso 1: Instalar BizTalk Server y configurar BAM

1. Instalar [BizTalk Server 2016](../../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md), o [BizTalk Server 2013 R2 / 2013](../../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md)e instalar la supervisión de la actividad económica (BAM).

2. Configurar [BizTalk Server](../../install-and-config-guides/configure-biztalk-server.md)y configurar la supervisión de la actividad económica (BAM).
  
3. Asegúrese de que tiene suficientes privilegios de seguridad para tener acceso a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. [Derechos de seguridad mínimos para BizTalk Server](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) es un recurso excelente.
  
## <a name="step-2-install-biztalk-accelerator-for-swift-a4swift"></a>Paso 2: Instalar el Acelerador de BizTalk para SWIFT (A4SWIFT)  

Instalar y configurar el [Acelerador de BizTalk para SWIFT](../../adapters-and-accelerators/accelerator-swift/install-configure-and-deploy-the-biztalk-accelerator-for-swift.md).

  
## <a name="step-3-install-swiftalliance-gateway-sag"></a>Paso 3: Instalar la puerta de enlace de SWIFTAlliance (SAG)  
 Antes de instalar a los adaptadores FileAct e InterAct, cree el SAG mensaje socios, dos puntos finales y las reglas de enrutamiento y probar la conectividad SAG en el equipo donde instale los adaptadores FileAct e InterAct.

Vea [https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway](https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway) para obtener detalles específicos sobre la puerta de enlace de SWIFTAlliance.  

## <a name="step-4-install-the-biztalk-fileact-and-interact-adapters"></a>Paso 4: Instalar a los adaptadores de BizTalk FileAct e InterAct  
  
1. Ejecute el **Setup.exe** como administrador para iniciar la instalación.  
  
2.  Seleccione **Instalar**.  
  
3.  Escriba el nombre de usuario y el nombre de la organización y, a continuación, seleccione **siguiente**.  
  
4.  **Aceptar** el contrato de licencia.
  
5.  En el **opciones de instalación** página, realice una de las siguientes acciones:  
  
    -   Seleccione el **completar** opción para instalar todos los componentes de la FileAct e interactuar adaptadores.  
  
    -   Seleccione el **personalizado** opción para elegir qué componentes va a instalar.  
  
     Compruebe la ubicación de instalación, o seleccione **examinar** para seleccionar una ubicación de instalación diferente. Seleccione **Siguiente**.  
  
6.  En el **resumen** página, seleccione **instalar** para instalar los componentes de la lista.  
  
    > [!NOTE]
    >  Cuando **ejecutar el Asistente para configuración** está activada (valor predeterminado), el **FileAct de BizTalk de Microsoft e interactuar configuración del adaptador** asistente se ejecuta automáticamente cuando se selecciona **finalizar**.  
  
7. Cuando se complete la instalación, seleccione **finalizar**. 

## <a name="next-steps"></a>Pasos siguientes

[Configure el adaptador de FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/configure-the-fileact-and-interact-adapter.md)  
[Mensajes de ejemplo interactuar y FileAct](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md)  
[Desinstalar o reparar el adaptador de FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[Lea la problemas conocidos de instalación](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)
  
## <a name="see-also"></a>Vea también  
[Introducción a los adaptadores FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)  
[Descripción de la arquitectura de adaptador FileAct e InterAct](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)