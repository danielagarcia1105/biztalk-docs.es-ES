---
title: Cómo configurar los vales de SSO | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], configuring tickets
- SSO, tickets
- tickets [SSO], configuring
ms.assetid: 32f0384b-ac79-4cce-b3f5-f4f8a73a673a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edec81ab1fa64ce7b4523771bb2c69b39c00bdfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018762"
---
# <a name="how-to-configure-the-sso-tickets"></a>Cómo configurar los vales de SSO
Se puede utilizar el Complemento MMC o la línea de comandos para controlar el comportamiento de los vales en la totalidad del sistema de inicio de sesión único; lo anterior incluye la posibilidad de permitir vales y la exigencia de que el sistema los valide.  
  
 Se pueden utilizar las opciones Sí, No, Activado o Desactivado para indicar si se permiten los vales y/o si se validan. El uso de mayúsculas y minúsculas en estas palabras carece de importancia y se deben utilizar independientemente de la configuración del idioma.  
  
 Si la característica Administración de SSO se encuentra instalado en un equipo remoto, se puede llevar a cabo una operación IssueTicket remota. Tenga en cuenta que se cifra todo el tráfico entre el módulo Administración de SSO y el módulo Tiempo de ejecución (servicio ENTSSO).  
  
 Al utilizar la utilidad de línea de comandos, ssomanage.exe, se puede especificar el tiempo de espera de vale en el nivel de aplicación afiliada únicamente al llevar a cabo una actualización de la aplicación, no a la hora de la creación.  
  
 Sólo un administrador de SSO puede configurar vales en el nivel de sistema de SSO y en el nivel de aplicación afiliada.  
  
 Si se deshabilita la compra de vales en el nivel del sistema, tampoco se podrá utilizar en el nivel de aplicación afiliada. Es posible habilitar los vales en el nivel de sistema y deshabilitarlos en el nivel de aplicación afiliada.  
  
 Si se habilita la validación en el nivel de sistema, también se requiere la validación de vales en el nivel de aplicación afiliada. Es posible deshabilitar la validación en el nivel de sistema y habilitarla en el nivel de aplicación afiliada.  
  
 Si el tiempo de espera de vales se especifica en el nivel de sistema y en el de aplicación afiliada, aquel que se especifique en el nivel de aplicación afiliada se utilizará para determinar la hora de expiración de vales.  
  
 Para obtener más información acerca de vales y validación de vales, consulte [vales de SSO](../core/sso-tickets.md).  
  
### <a name="to-configure-the-enterprise-single-sign-on-tickets-using-the-mmc-snap-in-for-the-affiliate-application"></a>Para configurar los vales de inicio de sesión único empresarial utilizando el Complemento MMC para la aplicación afiliada  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **aplicaciones afiliadas** nodo.  
  
3.  Haga clic en **aplicación afiliada**y, a continuación, haga clic en **propiedades**.  
  
4.  Haga clic en el **opciones** ficha.  
  
5.  Seleccione **permitir vales** y configure el tiempo de espera de vale según corresponda.  
  
### <a name="to-configure-the-enterprise-single-sign-on-system-level-tickets-using-the-command-line"></a>Para configurar los vales de nivel de inicio de sesión único empresarial mediante la línea de comandos  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo ** ssomanage – vales \<sí/no de permiten\> *\<validar sí/no\>**<em>, donde *\<sí/no de permiten\></em>  indica si se permitirán vales o no, y *\<validar sí/no\>* indica si los vales necesitará que se valida una vez canjeados.  
  
   > [!NOTE]
   >  Se pueden utilizar las opciones sí, no, activado o desactivado para indicar si se permiten los vales y/o si se validan. El uso de mayúsculas y minúsculas en estas palabras carece de importancia y se deben utilizar independientemente de la configuración del idioma.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Descripción de SSO](../core/understanding-sso.md)   
 [Uso de SSO](../core/using-sso.md)