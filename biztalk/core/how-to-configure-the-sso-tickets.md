---
title: Configurar los vales de SSO | Microsoft Docs
description: Utilice las administraciones de inicio de sesión único o una línea de comandos para permitir y validar único empresarial vales de sesión en el nivel de sistema y para las aplicaciones afiliadas en BizTalk Server.
ms.custom: ''
ms.date: 01/08/2019
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
ms.openlocfilehash: f3ce6c1de1a94225f06d09b66cc3e6c60c471f24
ms.sourcegitcommit: 2d39bcd10a22c5945d97a03988ccdc62f6fb3c93
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2019
ms.locfileid: "54443377"
---
# <a name="configure-the-sso-tickets-in-biztalk-server"></a>Configurar los vales de SSO en BizTalk Server
Puede utilizar MMC de administración de inicio de sesión único (SSO) empresarial o la línea de comandos para controlar el comportamiento de vale para todo el único inicio de sesión en sistema. Con las herramientas de este, puede permitir vales y validar vales de SSO.  
  
## <a name="before-you-begin"></a>Antes de comenzar

- Si la administración de SSO está instalado en un equipo remoto, puede ejecutar un control remoto [IssueTicket](https://docs.microsoft.com/biztalk/core/technical-reference/issoticket-issueticket-method) operación. Se cifra todo el tráfico entre el módulo de administración de SSO y el módulo de tiempo de ejecución (servicio ENTSSO).  
  
- Mediante la utilidad de línea de comandos ssomanage.exe, puede especificar el tiempo de espera de vale en el nivel de aplicación afiliada. Puede hacerlo sólo cuando se realiza una actualización de la aplicación, no cuando se crea la aplicación.
  
- Solo los usuarios del grupo de administradores de SSO pueden configurar vales en el nivel de sistema SSO y en el nivel de aplicación afiliada.  
  
- Si el control de vales está deshabilitado en el nivel de sistema, no se puede usar en el nivel de aplicación afiliada. Es posible habilitar los vales en el nivel de sistema y deshabilitarlos en el nivel de aplicación afiliada.  
  
- Si se habilita la validación en el nivel de sistema, se deben validar vales en el nivel de aplicación afiliada. Es posible deshabilitar la validación en el nivel de sistema y habilitarla en el nivel de aplicación afiliada.  
  
- Si se especifica el tiempo de espera de vale en el nivel de sistema y el nivel de aplicación afiliada, se introdujo en el nivel de aplicación afiliada determina el tiempo de expiración del vale.  
  
Para obtener más información acerca de vales y validación de vales, consulte [vales de SSO](../core/sso-tickets.md).  
  
## <a name="allow-affiliate-application-tickets-using-sso-administration"></a>Permitir vales de aplicación afiliada con la administración de SSO  
  
1.  Desde el **iniciar** menú, seleccione **todos los programas** > **Microsoft Enterprise Single Sign-On** > **administración de SSO** .
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **aplicaciones afiliadas** nodo.  
  
3.  Haga clic en **aplicación afiliada** > **propiedades**.  
  
4.  Elija la **opciones** ficha.  
  
5.  Seleccione **permitir vales** y escriba el tiempo de espera de vale que desee.  
  
## <a name="allow-and-validate-sso-system-level-tickets-using-the-command-line"></a>Permitir y validar vales de nivel de sistema SSO mediante la línea de comandos  
  
1. Abra un símbolo del sistema (menú Inicio > tipo **símbolo** > seleccione **símbolo**).

    > [!TIP]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba abrir el símbolo del sistema con privilegios administrativos (haga clic en **símbolo** > ** Ejecutar como administrador).
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es `\Program Files\Common Files\Enterprise Single Sign-On`. Por ejemplo, escriba: 

    `cd C:\Program Files\Common Files\Enterprise Single Sign-On`
  
3. Tipo `ssomanage -tickets <allowed yes/no> <validate yes/no>`, donde *\<sí/no de permiten\>* indica si se permiten los vales o no, y *\<validar sí/no\>* indica si se deben validar después de que se puede canjear vales.  
  
    Puede usar `yes`, `no`, `on`, o `off` para permitir o validar vales. El uso de mayúsculas y minúsculas en estas palabras carece de importancia y se deben utilizar independientemente de la configuración del idioma.
  
## <a name="see-also"></a>Vea también

[Descripción de SSO](../core/understanding-sso.md)   
[Uso de SSO](../core/using-sso.md)
