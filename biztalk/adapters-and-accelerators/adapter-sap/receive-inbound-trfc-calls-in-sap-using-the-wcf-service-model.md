---
title: Recibir llamadas de tRFC entrante en SAP mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving inbound using the WCF service model
- WCF service model, receiving inbound tRFC calls
ms.assetid: 02dc282b-b659-466a-8bd1-f400a05f71ec
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fb2091d0701831985a1975aa33bd5ecb667b443
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model"></a>Recibir llamadas de tRFC entrante en SAP mediante el modelo de servicio de WCF
Puede usar el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como un servidor RFC (tRFC) transaccional para recibir llamadas de tRFC entrada de SAP. Para tRFCs entrante, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite varios tRFCs en la misma unidad lógica de SAP de trabajo (LUW).  
  
 Las secciones de este tema proporcionan información acerca de cómo utilizar el adaptador como un servidor de tRFC en el modelo de servicio WCF.  
  
 También puede encontrar más información sobre el uso de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como un servidor de tRFC en los temas siguientes:  
  
-   Para obtener información general de la compatibilidad con tRFCs en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md). Debe leer este tema antes de continuar.  
  
-   Para obtener más información acerca de los esquemas de mensaje para las operaciones del servidor tRFC, consulte [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).  
  
## <a name="the-wcf-service-contract-for-a-trfc"></a>El contrato de servicio de WCF para una tRFC  
 Usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos de herramienta de utilidad ServiceModel (svcutil.exe) para generar un contrato de servicio WCF para el tRFCs que desea recibir desde el sistema SAP. El contrato generado para una entrada tRFC es similar al que se genera para una solicitud de cambio entrante salvo que:  
  
-   operaciones de tRFC aparecen bajo el nodo TRFC.  
  
-   El contrato de servicio WCF (interfaz) generado para tRFCs entrantes se denomina "Trfc". Debe especificar esta interfaz cuando se agrega el extremo de servicio al host de servicio. También es la interfaz que debe implementar el servicio WCF.  
  
    ```  
    public interface Trfc {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Trfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
        [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD/response")]  
        Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
    }  
    ```  
  
-   El contrato de mensaje de solicitud para las operaciones de TRFC tiene un parámetro GUID. Este es el GUID que se asigna al TID de SAP para el tRFC. En las operaciones del servidor de tRFC, el adaptador administra todas las llamadas a confirmar, deshacer y confirme el TID por el sistema SAP, así que no hay ninguna razón para usar explícitamente este GUID. Sin embargo, se puede utilizar para recuperar el TID de SAP desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante una llamada a **SapAdapterUtilities.ConvertGuidToTid**. Esto puede ser útil para ayudar a solucionar problemas en el sistema SAP.  
  
    ```  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
    [System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADD", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Trfc/", IsWrapped=true)]  
    public partial class Z_RFC_MKD_ADDRequest {  
  
        ...  
  
        public Z_RFC_MKD_ADDRequest(string DEST, System.Nullable<int> X, System.Nullable<int> Y, System.Guid TransactionalRfcOperationIdentifier) {  
            this.DEST = DEST;  
            this.X = X;  
            this.Y = Y;  
            this.TransactionalRfcOperationIdentifier = TransactionalRfcOperationIdentifier;  
        }  
    }  
  
    ```  
  
## <a name="how-do-i-enable-the-adapter-to-act-as-a-trfc-server"></a>¿Cómo se habilita el adaptador para actuar como un servidor de tRFC?  
 Para habilitar el adaptador para que actúe como un servidor de tRFC, debe establecer el **TidDatabaseConnectionString** propiedad de enlace en la cadena de conexión para la base de datos TID. Debe hacerlo antes de abrir el host del servicio. Se trata de la base de datos en el que el adaptador almacena la transacción de SAP TID (Id.) para cada tRFC. Para obtener más información acerca de esta propiedad de enlace, vea [obtener información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
## <a name="how-do-i-enlist-in-the-transaction-for-inbound-trfcs"></a>¿Cómo inscribirá en la transacción para tRFCs entrante?  
 Un SAP lógico unidad de trabajo (LUW) puede contener varios tRFCs. En el sistema SAP un LUW se identifica por un Id. de transacción único (TID). El adaptador crea una transacción confirmable para cada uno de los TID usado por el sistema SAP cuando invoca llamadas de tRFC en el adaptador. Cuando el sistema SAP invoca un tRFC en el adaptador; el adaptador pasa la transacción asociada con el TID de SAP para el servicio. Puede tener acceso a esta transacción que la transacción ambiente desde dentro del método de operación. Al dar de alta en esta transacción de ambiente, las acciones realizadas durante la operación de pueden participar en la LUW de SAP.  
  
 Para dar de alta en la transacción ambiente en un método de operación, debe:  
  
1.  Anotar el método de operación con el **TransactionScopeRequired** propiedad de la **OperationBehavior** atributo. Esto indica a WCF que desea tener acceso a la transacción de ambiente desde dentro de la operación.  
  
2.  Crear un ámbito de transacción anotando el método de operación con el **TransactionAutoComplete** propiedad de la **OperationBehavior** atributo o explícitamente usando un  **TransactionScope** dentro del método de operación.  
  
 En el ejemplo siguiente se muestra un servicio que implementa dos operaciones. Ambos métodos de operación se anotan con el **TransactionScopeRequired** propiedad para tener acceso a la transacción de ambiente.  
  
-   **Z_TRFC_EXAMPLE1** da de alta explícitamente en la transacción mediante el uso de un **TransactionScope** objeto.  
  
-   **Z_TRFC_EXAMPLE2** está anotada con la **TransactionAutoComplete** propiedad que se va a dar de alta en la transacción  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, UseSynchronizationContext = false)]  
class Z_Example_ServiceContractClass : Trfc  
{  
  
    // This operation method explicitly creates a TransactionScope to enlist in the ambient transaction  
    // You must explictly call ts.Complete to complete the transaction before you return from the operation  
    // Otherwise the transaction is aborted.  
    // You can throw an exception or return without calling ts.complete to abort the transacation  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public Z_TRFC_EXAMPLE1Response Z_TRFC_EXAMPLE1(Z_TRFC_EXAMPLE1Request request)  
    {  
        using (TransactionScope ts = new TransactionScope(TransactionScopeOption.Required))  
        {  
            // Process tRFC  
  
            ...  
  
            Z_TRFC_EXAMPLE1Response response = new Z_TRFC_EXAMPLE1Response();  
            response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
            return response;  
            //since there is no ts.Complete(), this is equivalent to a rollback.  
        }  
    }  
  
    // This operation method sets the TransactionAutoComplete property of the OperationBehavior attribute  
    // to enlist in the transaction. There is no need to explictly create a TransactionScope in the code.  
    // If the method returns with no unhandled exceptions, the transaction completes; otherwise it aborts  
    // You can throw an exception to abort the transaction.  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public Z_TRFC_EXAMPLE2Response Z_TRFC_EXAMPLE2(Z_TRFC_EXAMPLE2Request request)  
    {  
        // Process tRFC  
  
        ...  
  
        Z_TRFC_EXAMPLE2Response response = new Z_TRFC_EXAMPLE2Response();  
        response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
        return response;  
        //if there is no unhandled exception, the transaction completes when the operation returns.  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)