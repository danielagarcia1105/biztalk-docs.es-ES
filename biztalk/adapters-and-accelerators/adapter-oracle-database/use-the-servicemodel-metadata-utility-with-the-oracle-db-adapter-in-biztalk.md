---
title: Con la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para base de datos de Oracle en BizTalk Server | Documentos de Microsoft
description: "Utilizar svcutil.exe para un enlace no predeterminado, o para crear una clase de cliente de WCF o el contrato de servicio WCF con el adaptador de Oracle DB - módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8660014-da04-4692-89e8-f14fcb419496
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 143fefc3a35f70e08a9e1288cc019fe6561c2bb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-oracle-database"></a>Usar la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para base de datos de Oracle
Puede usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o un contrato de servicio WCF (interfaz) para las operaciones que el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone. Después de ejecutar svcutil.exe para generar una clase de cliente WCF o un contrato de servicio WCF, puede incluir el archivo generado en el código y crear instancias de la clase generada o implementar un servicio WCF desde el contrato para realizar operaciones en Oracle base de datos.  
  
 Mediante svcutil.exe requiere que proporcione un URI que contiene las credenciales de conexión. Dado que, de forma predeterminada, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] deshabilita las credenciales en el URI de conexión, debe configurar svcutil.exe para utilizar un enlace no predeterminado para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
 Las secciones siguientes muestran cómo configurar svcutil.exe y cómo utilizar svcutil.exe para generar código de cliente WCF o un contrato de servicio WCF con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
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
          \<!-- the name should match the required scheme of the WS-Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="oracledb"  
                    binding="oracleDBBinding"  
                    bindingConfiguration="OracleDBBinding"  
                    contract="IMetadataExchange" />  
        </client>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" acceptCredentialsInUri="true" />  
            </oracleDBBinding>  
        </bindings>  
  
      \</system.serviceModel>  
  
    </configuration>  
    ```  
  
> [!NOTE]
>  Puede establecer cualquiera de las propiedades de enlace de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en la configuración de enlace.  
  
 Para obtener más información acerca de cómo configurar un enlace no predeterminado para svcutil.exe, vea el tema "Extremo de metadatos seguros personalizada" en la documentación de WCF en [http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077).  
  
### <a name="configure-a-non-default-binding-for-the-pollingstmt-operation"></a>Configurar un enlace para la operación POLLINGSTMT no predeterminado  
 Para utilizar svcutil.exe para crear un contrato de servicio WCF para la operación de POLLINGSTMT, debe configurar el enlace no predeterminado para incluir la **pollingStatement** propiedad, además de **acceptCredentialsInUri**. El **pollingStatement** debe contener la instrucción SELECT que tenga como destino de la tabla. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usan esta propiedad para generar la clase que representa el resultado fuertemente tipado establecido devueltos por la operación de POLLINGSTMT. En el ejemplo siguiente se muestra una configuración de enlace que se usa para generar un contrato de servicio WCF para una operación de POLLINGSTMT que tiene como destino en la tabla /SCOTT/EMP.  
  
```  
<bindings>  
    <oracleDBBinding>  
        <binding name="OracleDBBinding" acceptCredentialsInUri="true"   
                                   pollingStatement="SELECT * FROM EMP FOR UPDATE" />  
    </oracleDBBinding>  
</bindings>  
```  
  
## <a name="create-a-wcf-client-class-or-wcf-service-contract-with-svcutilexe"></a>Cree una clase de cliente WCF o el contrato de servicio WCF con svcutil.exe  
 Utilizar svcutil.exe para generar código de cliente WCF o un contrato de servicio WCF (interfaz) para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], debe proporcionar un URI que especifica un punto de conexión de WS-Metadata Exchange (MEX) y la o las operaciones que se desea svcutil.exe a de conexión generar código. También debe especificar credenciales de conexión para la base de datos de Oracle en el URI de conexión.  
  
> [!NOTE]
>  Para poder usar svcutil.exe con la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], debe configurarlo para usar un valor no predeterminado de enlace; para obtener información acerca de cómo hacerlo, consulte [configurar svcutil.exe para el adaptador de la base de datos de Oracle](#BKMK_ConfigureSvcutil).  
  
 Especificar una operación de punto de conexión y de destino MEX en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] URI de conexión de la siguiente manera:  
  
-   Debe incluir el parámetro "wsdl" en el query_string. Si es el primer parámetro de la query_string, se especifica justo después del signo de interrogación (?). Si no es el primer parámetro, debe ir precedida por una y comercial (&).  
  
-   Debe seguir el parámetro "wsdl" por uno o más parámetros de "op". Cada parámetro de "op" está precedido por una y comercial (&) y especifica el identificador del nodo de una operación de destino.  
  
 Los tres ejemplos siguientes muestran cómo elegir como destino varias operaciones mediante el uso de svcutil.exe.  
  
 Este ejemplo crea una clase de cliente WCF para una operación de inserción en la tabla /SCOTT/EMP.  
  
 **. \svcutil "oracledb://User=SCOTT; Contraseña =TIGER@ADAPTER? wsdl & op = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert "**  
  
 En este ejemplo se crea una clase de cliente WCF para la inserción y las operaciones de eliminación en la tabla /SCOTT/EMP.  
  
 **. \svcutil "oracledb://User=SCOTT; Contraseña =TIGER@ADAPTER? wsdl & op = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert & op = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete "**  
  
 Este ejemplo crea un contrato de servicio WCF para la operación de POLLLINGSTMT. (Para utilizar svcutil.exe para generar un contrato de servicio WCF para la operación de POLLINGSTMT, debe configurar un enlace no predeterminado para svcutil.exe que incluye una instrucción de sondeo.)  
  
 **. \svcutil "oracledb://User=SCOTT; Contraseña =TIGER@ADAPTER? wsdl & op = http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT "**  
  
> [!IMPORTANT]
>  Debe colocar el URI de conexión entre comillas en la línea de comandos. En caso contrario, svcutil.exe intenta recuperar metadatos para las operaciones que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite. Los resultados de un intento de este tipo son indefinidos.  
  
 De forma predeterminada, svcutil.exe coloca el código generado en el archivo output.cs; Sin embargo, puede cambiar el nombre del archivo de salida y muchas otras opciones que svcutil.exe utiliza estableciendo los modificadores de línea de comandos. Para obtener más información acerca de las opciones que svcutil.exe admite, vea el tema "ServiceModel Metadata Utility Tool (Svcutil.exe)" en la documentación de WCF en [http://go.microsoft.com/fwlink/?LinkId=72777](http://go.microsoft.com/fwlink/?LinkId=72777).  
  
 Svcutil.exe no proporciona la capacidad de búsqueda para las operaciones (por ejemplo, mediante caracteres comodín). Debe especificar explícitamente los identificadores de nodo para las operaciones específicas que desee cambiar. No se puede especificar identificadores que hacen referencia solo a las categorías de nodo. Para obtener más información acerca de los identificadores de nodo que la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).  
  
 El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] proporciona exploración avanzada y capacidades de búsqueda que pueden simplificar en gran medida la generación de una clase de cliente WCF y el contrato de servicio WCF. Para obtener más información sobre la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio de WCF para artefactos de solución de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)