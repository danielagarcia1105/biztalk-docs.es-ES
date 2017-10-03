---
title: Configurar el Acelerador de BizTalk para SWIFT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e34b0b2d-f563-468b-b6b9-536f0df96f52
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaa9812243ef7d5ff4bb8b902ac7aee48e54ab99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-biztalk-accelerator-for-swift"></a>Configurar el Acelerador de BizTalk para SWIFT

Configurar la [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]. 

Al instalar [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)], hay una casilla que permite ejecutar la configuración automáticamente. O bien, puede abrir la configuración BizTalk Accelerator for SWIFT (A4SWIFT) aparece en las aplicaciones.

En este tema se muestra cómo configurar el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] acelerador, cómo exportar o importar una configuración y también se enumeran los pasos posteriores a la configuración.

## <a name="configure-a4swift"></a>Configurar A4SWIFT

1. Abra el Acelerador de BizTalk para SWIFT (A4SWIFT) configuración.
2. Seleccione **MCRR**. MCRR solo está disponible si ha instalado el **reparación de mensajes y nuevo envío** componentes.
3. Cuando se le pregunte **¿desea crear un nuevo grupo de base de datos**:

  * Seleccione esta opción para crear los nuevos grupos que se muestra en el **grupo** panel. 
  * Para unirse a un grupo de base de datos existente, desactive esta opción.

3. Si instaló **componentes Web de reparación de mensajes y nuevo envío**, a continuación, seleccione **WebService**.
4. Seleccione el sitio web para hospedar el servicio Web de A4SWIFT. De forma predeterminada, se selecciona el sitio Web predeterminado.
5. Seleccione **aplicar configuración**.
6. En **resumen**, compruebe los valores de configuración y, a continuación, haga clic en **configurar**. 

    > [!TIP] 
    > Puede guardar los ajustes de configuración como archivo XML, si lo desea.

7. Seleccione **finalizar** cuando se completa la configuración.

## <a name="export-or-import-a-configuration"></a>Exportar o importar una configuración
Puede exportar la configuración de A4SWIFT en un archivo XML. A continuación, se puede importar esta configuración para configurar otra instalación de A4SWIFT. 

### <a name="export-the-configuration"></a>Exportar la configuración

1. Abra el Acelerador de Microsoft BizTalk para SWIFT configuración y seleccione **Exportar configuración**.
2. En **Guardar como**, vaya a la carpeta donde desea guardar el archivo de configuración, escriba un nombre para el archivo de configuración y, a continuación, **guardar**.
3. Cuando se exportan correctamente, seleccione **Aceptar**.

### <a name="import-a-configuration"></a>Importar una configuración
1. Abra el Acelerador de Microsoft BizTalk para SWIFT configuración y seleccione **importar configuración**.
2. Vaya a la carpeta que contiene el archivo de configuración, seleccione el archivo y, a continuación, seleccione **importación**.

## <a name="post-configuration-steps"></a>Pasos posteriores a la configuración

### <a name="add-users-to-the-a4swift-users-group"></a>Agregar usuarios al grupo usuarios de A4SWIFT

Después de configurar la [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)], agregar la cuenta que ejecuta la instancia de host BizTalkServerApplication para el **A4SWIFT usuarios** grupo (*no* el **administradores de A4SWIFT** grupo). 

**Pasos**:

1. Abra **Services**. Los servicios también está disponible en **el administrador del servidor**y, a continuación, **herramientas**. 
2. En la lista, busque **grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication**. 
3. Doble: seleccione esta opción para abrir sus propiedades.
4. En el **iniciar sesión** ficha, tenga en cuenta la cuenta de usuario aparece como **esta cuenta**.
5. Abra **usuarios y grupos locales** (en administración de equipos) y, a continuación, busque la **A4SWIFT usuarios** grupo. Agregue la cuenta de usuario a este grupo.

> [!TIP] 
> La cuenta de instancia de host necesita esta pertenencia a grupos para el componente de tiempo de ejecución de reparación de mensajes de host para tener acceso a la base de datos de BizTalk Server.

### <a name="check-the-identity-of-the-application-pool"></a>Comprobar la identidad del grupo de aplicaciones
El servicio web de A4SWIFT_MRSR se hospeda en una aplicación en IIS. La identidad del grupo de aplicaciones *no* ser servicio de red. Cambie la identidad del grupo de aplicaciones a una cuenta local o de dominio que sea miembro de la **A4SWIFT usuarios** grupo.

**Pasos**:

1. Abra **Administrador de Internet Information Services**. El Administrador de IIS también está disponible en **el administrador del servidor**y, a continuación, **herramientas**. 
2. Expanda el **sitio Web predeterminado**y seleccione el servicio web de A4SWIFT_MRSR. 
3. Seleccione **configuración básica**. Se muestra el nombre del grupo de aplicaciones.
4. En el panel izquierdo, seleccione **grupos de aplicaciones**y, a continuación, seleccione el grupo de aplicaciones.
5. Seleccione **configuración avanzada**y cambie el **identidad** si es necesario.