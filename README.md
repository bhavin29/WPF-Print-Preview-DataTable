WPF Print & Preview DataTable Class
===================


**WPF Utility class that helps you to Print & Preview DataTable**

----------

How To Use
-------------
In   **XAML**

    <FlowDocumentReader>
            <FlowDocument Name="flowDocument" ColumnWidth="999999">
                <Paragraph Name="headParagraph" FontSize="20" FontWeight="Bold">Header Paragraph</Paragraph>
                <Paragraph Name="ndHeadParagraph" FontSize="15">nd Header Paragraph</Paragraph>
            </FlowDocument>
    </FlowDocumentReader>
    <Button Name="printButton" Content="Print Click="printButton_Click" />

In   **Code Behind**
            
            // Simple Scenario Example 
            WPFPrintUtility wPFPrintUtility = new WPFPrintUtility();
            wPFPrintUtility.CreateAndVisualizeDataTable(flowDocument, mockDataTable, "2017 Sales Project", "My Footer");
            ---------------OR----------------------
            //Sure you should replace this dataTable by your actual datatable.
            DataTable mockDataTable = wPFPrintUtility.CreateMockDataTableForTest();
            GlobalFormating.DataRowsEvenBrush = Brushes.AliceBlue;
            wPFPrintUtility.CreateAndVisualizeDataTable(flowDocument, mockDataTable, "2017 Sales Project", "My Footer");
            //wPFPrintUtility.CreateAndVisualizeDataTable(flowDocument, mockDataTable, null, null); 
            ---------------OR----------------------
            //Sure you should replace this dataTable by your actual datatable.
            DataTable mockDataTable = wPFPrintUtility.CreateMockDataTableForTest();
            GlobalFormating.DataRowsEvenBrush = Brushes.AliceBlue;
            Table table = wPFPrintUtility.CreateAndVisualizeDataTable(mockDataTable, "2017 Sales Project", "My Footer");
            flowDocument.Blocks.Add(table);
            ---------------OR-----------------------
           //Sure you should replace this dataTable by your actual datatable.
            DataTable mockDataTable = wPFPrintUtility.CreateMockDataTableForTest();
            wPFPrintUtility.Datatable = mockDataTable;
            wPFPrintUtility.HeaderTitleText = "2017 Sales Project";
            wPFPrintUtility.FooterText = "My Footer";
            GlobalFormating.DataRowsEvenBrush = Brushes.AliceBlue;
            Table table = wPFPrintUtility.CreateAndVisualizeDataTable();
            flowDocument.Blocks.Add(table);
            
            ------------- Print Click --------------
            private void printButton_Click(object sender, RoutedEventArgs e)
                {
                    wPFPrintUtility.Print(flowDocument);
                }



