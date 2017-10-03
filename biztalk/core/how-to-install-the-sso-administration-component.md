---
title: "Instalar el componente de administración de SSO | Documentos de Microsoft"
description: "Realice una instalación personalizada para obtener la administración de SSO y use ssomanage o administración de SSO para especificar el nombre del servidor de BizTalk Server"
ms.custom: 
ms.date: 09/27/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 096839e2-7129-498d-92ee-5afeea8dbe0d
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab2bb01defe700408a551a144eae67d0405565f4
ms.sourcegitcommit: 5355a25d120d094778fb8f68ea14cab55c68d292
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2017
---
# <a name="how-to-install-the-sso-administration-component"></a>Cómo instalar el componente de administración de SSO

## <a name="overview"></a>Información general
Puede instalar el componente de administración de inicio de sesión único de empresa como una característica independiente. Esto resulta de utilidad si se necesita administrar el sistema SSO de forma remota. Los requisitos de hardware y software son los mismos que los de una instalación típica de los servicios de tiempo de ejecución de SSO empresarial.  
  
 Después de instalar el componente de administración, especifique el servidor de SSO que se usará para administración. Puede hacerlo con la herramienta de línea de comandos (ssomanage.exe), o el complemento de MMC de administración de SSO. Ambos procedimientos se muestran en este tema.  
  
 Con la instalación de la utilidad administrativa de SSO (ssomanage.exe), no se crean accesos directos en el menú Inicio para obtener acceso a las utilidades de la línea de comandos. Para ejecutar las utilidades administrativas de SSO después de la instalación, debe abrir un símbolo del sistema y navegue hasta el directorio SSO en `Program Files\Common Files\Enterprise Single Sign-On`.  
  
 La característica de administración de SSO empresarial también incluye un complemento de MMC. MMC 3.0 debe instalarse en el equipo para el complemento de función.  
  
 Para abrir el complemento de MMC de SSO empresarial de la **iniciar** menú, seleccione **todos los programas**, seleccione **Microsoft Enterprise Single Sign-On**y, a continuación, **SSO Administración**.  
  
## <a name="install-the-enterprise-single-sign-on-administrative-component"></a>Instalar el componente administrativo de Enterprise Single Sign-On  
  
-   Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y seleccione únicamente la característica de administración de inicio de sesión único de empresa. Para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], este aparece en **Software adicional**.  
  
## <a name="enter-the-server-using-the-mmc-snap-in"></a>Especifique el servidor mediante el complemento de MMC  
  
1.  Tras instalar el componente administrativo en un equipo en el que no se encuentre instalado aún, abra el complemento de administración de SSO.  
  
     En el **iniciar** menú, seleccione **todos los programas**, seleccione **Microsoft Enterprise Single Sign-On**y, a continuación, seleccione **administración de SSO**.  
  
2.  En el complemento MMC en el **raíz de consola**, haga clic en **Enterprise Single Sign-On**y haga clic en **seleccione**.  
  
     El **Seleccionar servidor de SSO** aparecerá el cuadro de diálogo.  
  
3.  Especifique el nombre del servidor de SSO o desplácese hasta el que desee. Para especificar el servidor de SSO para todos los usuarios en el equipo, seleccione **establecer servidor de SSO para todos los usuarios**.  
  
4.  Haga clic en **Aceptar**.  
  
## <a name="enter-the-server-using-the-command-line-tool"></a>Especifique el servidor mediante la herramienta de línea de comandos  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es `\Program Files\Common Files\Enterprise Single Sign-On`.  
  
3.  Especifique el servidor de SSO seleccionando una de las siguientes opciones:  
  
    1.  Tipo de **ssomanage – server** para especificar el servidor de SSO al que desea conectarse a cuando se realizan operaciones de administración.  
  
         \- O BIEN  
  
    2.  Tipo de **ssomanage - serverall** para especificar el servidor de SSO todos los usuarios de este equipo se conectará al realizar operaciones de administración.  
  
## <a name="see-also"></a>Vea también  
 [Cómo instalar la utilidad de cliente SSO](../core/how-to-install-the-sso-client-utility.md)   
 [Configuración de SSO](../core/configuring-sso.md)   
 [Instalación de SSO](../core/installing-sso.md)
