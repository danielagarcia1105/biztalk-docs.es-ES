---
title: Usar la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para aplicaciones Siebel eBusiness | Documentos de Microsoft
description: "Utilizar svcutil.exe para un enlace no predeterminado, o para crear una clase de cliente de WCF o el contrato de servicio WCF con el adaptador de Siebel - módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03d16481-cc8b-4e28-a33c-92e48a9a7e8f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0c2c016387f6b70870e04b211b0bdfe047de11d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-siebel-ebusiness-applications"></a>Usar la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para Siebel eBusiness Applications
Puede usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF para las operaciones que el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] expone. Después de ejecutar svcutil.exe para generar una clase de cliente WCF, puede incluir el archivo generado en el código y crear instancias de la clase de cliente WCF para realizar operaciones en el sistema Siebel.  
  
 Mediante svcutil.exe requiere que proporcione un URI que contiene las credenciales de conexión. Dado que, de forma predeterminada, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] deshabilita las credenciales en el URI de conexión, debe configurar svcutil.exe para utilizar un enlace no predeterminado para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. También puede configurar otras propiedades de enlace en el enlace no predeterminado.  
  
 Las secciones siguientes muestran cómo configurar svcutil.exe y cómo utilizar svcutil.exe para generar el código de cliente WCF con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
##  <a name="BKMK_ConfigureSvcutil"></a>Configurar svcutil.exe para un enlace no predeterminado   
 Para configurar svcutil.exe para utilizar un enlace no predeterminado, debe crear una copia local de svcutil.exe y, a continuación, crear o modificar una copia local del archivo de configuración svcutil.exe.config.  
  
 
1.  Cree una carpeta y copie svcutil.exe en la nueva carpeta. Normalmente puede encontrar svcutil.exe en la ubicación de instalación de Windows SDK, específicamente, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.  
  
2.  Cree un archivo denominado svcutil.exe.config en la nueva carpeta.  
  
3.  Agregar un enlace y un punto de conexión de cliente en el archivo svcutil.exe.config. Debe ejecutar svcutil.exe desde la nueva carpeta para asegurarse de que se usa la configuración correcta.  
  
    > [!IMPORTANT]
    >  El atributo de nombre del extremo del cliente debe especificar el esquema utilizado en el URI de conexión. Este valor distingue mayúsculas de minúsculas.  
  
    ```  
    <configuration>  
      \<system.serviceModel>  
        <client>  
          \<!-- the name should match the required scheme of the Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="siebel"  
            binding="siebelBinding"  
            bindingConfiguration="SiebelBinding"  
            contract="IMetadataExchange" />  
        </client>  
        <bindings>  
          <siebelBinding>  
            <binding name="SiebelBinding" acceptCredentialsInUri="true" />  
          </siebelBinding>  
        </bindings>  
  
      \</system.serviceModel>  
  
    </configuration>  
  
    ```  
  
> [!NOTE]
>  Puede establecer cualquiera de las propiedades de enlace de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en la configuración de enlace.  
  
 Para obtener más información acerca de cómo configurar un enlace no predeterminado para svcutil.exe, vea el tema "Extremo de metadatos seguros personalizada" en la documentación de WCF en [http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077).  
  
## <a name="creating-a-wcf-client-class-with-svcutilexe"></a>Crear una clase de cliente WCF con svcutil.exe  
 Utilizar svcutil.exe para generar código de cliente WCF para la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], debe proporcionar una conexión de URI que especifica un **IMetadataExchange** (mex) punto de conexión y la operación u operaciones desea svcutil.exe para generar código. También debe especificar las credenciales de conexión para el sistema Siebel en el URI de conexión.  
  
> [!NOTE]
>  Para poder usar svcutil.exe con la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], debe configurarlo para usar un valor no predeterminado enlace; para obtener información acerca de cómo hacerlo, consulte [configuración de svcutil.exe para el adaptador de Siebel](#BKMK_ConfigureSvcutil).  
  
 Especificar una operación de punto de conexión y de destino de mex en el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] URI de conexión de la siguiente manera:  
  
-   Debe incluir el parámetro "wsdl" en el query_string. Si es el primer parámetro de la query_string, se especifica justo después del signo de interrogación (?). Si no es el primer parámetro, debe ir precedida por una y comercial (&).  
  
-   Debe seguir el parámetro "wsdl" por uno o más parámetros de "op". Cada parámetro de "op" está precedido por una y comercial (&) y especifica el identificador del nodo de una operación de destino.  
  
 Los dos ejemplos siguientes muestran cómo elegir como destino varias operaciones mediante el uso de svcutil.exe.  
  
 Este ejemplo crea una clase de cliente WCF para una operación de inserción en el objeto de negocios ACCOUNT\ACCOUNT.  
  
 **. \svcutil "siebel://Username=YourUserName; ¿Contraseña =YourPassword@Siebel_server:1234? SiebelEnterpriseServer = ent_server & SiebelObjectManager = obj_mgr & Language = enu wsdl & op = http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert "**  
  
 Este ejemplo crea una clase de cliente WCF para una operación de inserción y una operación de eliminación en el objeto de negocios ACCOUNT\ACCOUNT.  
  
 **. \svcutil "siebel://Username=YourUserName; ¿Contraseña =YourPassword@Siebel_server:1234? SiebelEnterpriseServer = ent_server & SiebelObjectManager = obj_mgr & Language = enu wsdl & op = http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert & op = http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete "**  
  
> [!IMPORTANT]
>  Debe colocar el URI de conexión entre comillas en la línea de comandos. En caso contrario, svcutil.exe intenta recuperar metadatos para las operaciones que el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no admite. Los resultados de un intento de este tipo son indefinidos.  
  
 De forma predeterminada, svcutil.exe coloca el código generado en el archivo output.cs; Sin embargo, puede cambiar el nombre del archivo de salida y muchas otras opciones que svcutil.exe utiliza estableciendo los modificadores de línea de comandos.  
  
 Svcutil.exe no proporciona la capacidad de búsqueda para las operaciones (por ejemplo, mediante caracteres comodín). Debe especificar explícitamente los identificadores de nodo para las operaciones específicas que desee cambiar. No se puede especificar identificadores que hacen referencia solo a las categorías de nodo. Para obtener más información acerca de los identificadores de nodo que la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] superficies, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).  
  
 El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] proporciona funcionalidades de búsqueda que pueden simplificar en gran medida la generación de una clase de cliente WCF y examinar avanzada. Para obtener más información sobre la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Siebel](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).  
  
