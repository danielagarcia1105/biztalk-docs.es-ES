---
title: Cómo instalar la utilidad de cliente de inicio de sesión único | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, client utility
- client utility [SSO]
- SSO, installing
ms.assetid: e14d257e-2fde-46af-b90c-5dbc0884536b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674ecc3857fe9e5b5cbef2914aec875f350d7de5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003965"
---
# <a name="how-to-install-the-sso-client-utility"></a>Cómo instalar la utilidad de cliente SSO
La utilidad de cliente de SSO independiente (basada en una interfaz de usuario y en una utilidad de línea de comandos) permite a los usuarios finales configurar sus asignaciones cliente en la base de datos de SSO. Puede instalar la utilidad de cliente desde un archivo autoextraíble (SSOClientInstall.exe) instalado con la característica de administración de SSO. Los administradores también pueden hacer que el paquete del instalador esté disponible para los usuarios cliente al colocar una copia del paquete del instalador en un recurso compartido de red.  
  
 Para instalar la utilidad de cliente de SSO, debe ejecutar uno de los siguientes sistemas operativos en el equipo cliente:  
  
- [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]  
  
- [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] o [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] (solo es necesario si usa la utilidad de cliente de SSO basada en la interfaz de usuario o aprovecha el componente de interoperabilidad administrado de SSO empresarial).  
  
  Después de instalar la utilidad de cliente de SSO, puede iniciarla desde el **iniciar** menú haciendo **programas**, **Microsoft Enterprise Single Sign-On**y, a continuación, **Utilidad de cliente SSO**.  
  
### <a name="to-install-the-sso-client-utility"></a>Para instalar la utilidad de cliente de SSO  
  
1.  Haga doble clic en SSOClientInstall del paquete del instalador.  
  
    > [!NOTE]
    >  Pídale al administrador de inicio de sesión único empresarial que le indique la ubicación de este archivo en su empresa.  
  
     El **WinZip Self-Extractor** programa aparece.  
  
2.  Seleccione la carpeta donde desee descomprimir los archivos y haga clic en **Unzip**.  
  
     Se recomienda descomprimir los archivos en una carpeta temporal.  
  
     El **Enterprise Single Sign-On instalación del cliente** programa aparece.  
  
3.  En **la bienvenida al cliente Enterprise Single Sign-On** página, haga clic en **siguiente**.  
  
4.  En la página Contrato de licencia, haga clic en **acepto los términos de este contrato de licencia**y, a continuación, haga clic en **siguiente**.  
  
5.  En el **información del usuario** página, escriba el nombre de usuario, el nombre de la organización y, a continuación, haga clic en **siguiente**.  
  
6.  En el **Iniciar instalación** página, haga clic en **instalar**.  
  
7.  En el **finalización del Enterprise Single Sign-On cliente asistente** página, haga clic en **finalizar**.  
  
8.  Especifique el servidor de SSO mediante una de las siguientes opciones:  
  
    -   Abra el complemento MMC de administración de ENTSSO. El **Seleccionar servidor de SSO** aparecerá el cuadro de diálogo. Escriba o busque el servidor de SSO con el que se desea efectuar la conexión al llevar a cabo las operaciones de administración. Para especificar el servidor de SSO para todos los usuarios en el equipo, seleccione **establecer servidor de SSO para todos los usuarios**.  
  
         O BIEN  
  
    -   En un símbolo del sistema, escriba `ssomanage –server` para especificar el servidor de SSO que desee. También puede escribir `ssomanage -serverall` para especificar el servidor SSO que todos los usuarios de este equipo se conectará al realizar operaciones de administración.  
  
## <a name="see-also"></a>Vea también  
 [Cómo instalar el componente de administración de SSO](../core/how-to-install-the-sso-administration-component.md)   
 [Configuración de SSO](../core/configuring-sso.md)   
 [Instalación de SSO](../core/installing-sso.md)