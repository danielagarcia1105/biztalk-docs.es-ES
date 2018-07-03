---
title: Solucionar problemas de instalación con el adaptador de SQl | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48778158-6064-4731-be72-1af855ebe373
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9543c7dcd4c92cfd15aed5b93115ffc9a849652b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001461"
---
# <a name="troubleshoot-installation-issues-with-the-sql-adapter"></a>Solucionar problemas de instalación con el adaptador de SQl
> [!IMPORTANT]
>  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] está disponible como parte de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] , así como un adaptador independiente. Si tiene acceso a este tema para conocer los problemas de instalación de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] que es independiente de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], todas las referencias a la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] el programa de instalación debe interpretarse como [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] el programa de instalación.  

 Instalación de Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copia los archivos binarios del producto en el equipo y registra los enlaces para cada adaptador. En esta sección se analiza el uso de técnicas de solución de problemas para resolver errores de instalación.  

## <a name="logging-messages-for-setup-actions"></a>Mensajes de registro de acciones de instalación  
 El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación realiza las tareas de instalación estándar la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Además, el programa de instalación también lleva a cabo determinadas acciones como el registro de los enlaces del adaptador personalizados. Puede registrar mensajes para las acciones estándares como personalizadas que realiza la instalación.  

- El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] programa de instalación instala los archivos específicos del adaptador mediante MSI. Por lo tanto, el registro para el programa de instalación es el registro de MSI estándar.  

- Todos los registros de las acciones personalizadas que realiza el programa de instalación están disponibles en % TEMP%\adaptersetup.log. Si se produce un error en el seguimiento en el archivo de registro, los seguimientos también están disponibles en el registro de eventos.  

## <a name="known-issues"></a>Problemas conocidos  
 Los siguientes son los errores más comunes que pueden surgir al instalar el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], junto con su causa y resolución.  



###  <a name="BKMK_SQLSetupBinding"></a> Se produce un error en el programa de instalación registrar los enlaces del adaptador  
 **Problema**  

 Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Asistente para la instalación no puede registrar los enlaces del adaptador, pero continúa con la instalación del adaptador.  

 **Causa**  

 Esto podría producir debido a problemas con [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] instalación, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] instalación o el archivo machine.config estén dañados. Los enlaces del adaptador se escriben en el archivo machine.config.  

 **Resolución**  

 Se debe registrar manualmente el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enlace.  

##### <a name="to-register-the-adapter-binding"></a>Para registrar el enlace del adaptador  

1. Navegue al archivo machine.config en el equipo. Por ejemplo, en una plataforma de 32 bits, está disponible en el archivo machine.config \<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.  

    En esta ruta de acceso, \<versión\> es la versión de .NET Framework.  

2. Abra el archivo con un editor de texto.  

3. Para registrar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enlace:  

   1. Busque el elemento "system.serviceModel" y agregue lo siguiente en él:  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. Busque el elemento "bindingElementExtensions" bajo system.serviceModel\extensions.  

   3. Busque el campo que falta [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enlace. Agregue la siguiente sección en el nodo "bindingElementExtensions".  

       Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. Busque el elemento "bindingExtensions" bajo system.serviceModel\extensions.  

   5. Busque el campo que falta [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enlace. Agregue la siguiente sección en el nodo "bindingExtensions".  

       Para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], agregue:  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  Para obtener información sobre cómo determinar la clave pública y la versión, consulte [determinar la clave pública y la versión](#BKMK_PubKey).  

4. Guarde y cierre el archivo machine.config.  

####  <a name="BKMK_PubKey"></a> Determinación de la clave pública y versión  
 Realice los pasos siguientes para determinar la clave pública para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

###### <a name="to-determine-the-public-key"></a>Para determinar la clave pública  

1. Navegue hasta el directorio de Windows, normalmente C:\WINDOWS\assembly.  

2. Haga clic en el archivo DLL para el que desea que la clave pública y la versión y, a continuación, seleccione **propiedades**. En la tabla siguiente se muestra el nombre del archivo DLL para [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  


   |                              Adaptador                              |    Nombre del archivo DLL     |
   |-------------------------------------------------------------------|------------------------|
   | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] | Microsoft.Adapters.Sql |


3. En el **General** pestaña, el valor con el **Token de clave pública** etiqueta Especifica la clave pública para el archivo DLL. De forma similar, valor frente a la **versión** etiqueta Especifica el número de versión para el archivo DLL.  

4. Copie la clave pública y, a continuación, haga clic en **cancelar**.  

###  <a name="BKMK_SQLConsumeBinding"></a> Error al usar el complemento Consume Adapter Service o Add Adapter Service Reference complemento en una instalación de 64 bits  
 **Problema**  

 Mediante el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] en un equipo de 64 bits con la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] da como resultado el siguiente error:  

```  
No valid adapters are installed on this machine  
```  

 **Causa**  

 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config. Una plataforma de 64 bits tiene machine.config dos archivos, uno utilizados por las aplicaciones de 32 bits y la otra se usa por las aplicaciones de 64 bits. Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config. Sin embargo, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se ejecuta como un proceso de 32 bits y, por tanto, cuando inicie la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], comprueba los enlaces en la versión de 32 bits del archivo machine.config del complemento y se produce un error a un error.  

 **Resolución**  

 Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.  

> [!IMPORTANT]
>  Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación. Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.  

###  <a name="BKMK_SQLInvalidBinding"></a> Error de enlace no válido durante la configuración de puertos de adaptador de SQL en la consola de administración de BizTalk Server en una instalación de 64 bits  
 **Problema**  

 Al intentar configurar un puerto para el adaptador en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, obtendrá el error siguiente:  

```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sqlBinding".  
Verify the binding extension is registered in machine.config."  
```  

 **Causa**  

 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es un enlace personalizado de WCF, que está registrado en System.ServiceModel en el archivo machine.config. Una plataforma de 64 bits tiene machine.config dos archivos, uno utilizados por las aplicaciones de 32 bits y la otra se usa por las aplicaciones de 64 bits. Por lo tanto, cuando se instala la versión de 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], el Asistente para instalación registra los enlaces en la versión de 64 bits del archivo machine.config. Sin embargo, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración que se ejecuta como un proceso de 32 bits y, por tanto, al configurar un puerto para el adaptador, comprueba los enlaces en la versión de 32 bits del archivo machine.config y se produce un error a un error.  

 **Resolución**  

 Instale las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación.  

> [!IMPORTANT]
>  Solo debe tener 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] instalación. Instalación en paralelo de 32 bits y 64 bits [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no se admite en un único equipo.  

## <a name="see-also"></a>Vea también  
 [Solucionar problemas del adaptador SQL](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)