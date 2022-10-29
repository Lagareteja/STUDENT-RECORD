# STUDENT-RECORD
one another about students' information.This system help to make it easier for the teacher and parents to track and know the information of the students, who enrolled in the school and make them to easier to insert, search, show, and delete in the students record.The goal of student record system that we propose is to separate student records are connected or made accessible to carry out one or more essential tasks. These tasks could involve , inserting/adding/deleting records, show and search the record . Student record systems can be stored in several ways, just like individual student records: as paper files in filing cabinets, on microfilm, in computer files, or using a combination of modalities. Separate student records become a student record system when they are linked together or made available to perform of one or more that can access not only by the teachers, but can students can view but they are not authorized to delete what in the system, but they can check it whether if their information correctly entered in the record
Programmers
Ladyjestin Agustin
Mary Grace Lagarteja
Christian Eugenio
Karl Howard Solis
Date Submitted: 10-29-2022
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Studnt_Record
{
    public partial class Form1 : Form
    {
        DataTable table = new DataTable("table");
        int index;
        public Form1()
        {

            InitializeComponent();

        }

        private void Form1_Load(object sender, EventArgs e)
        {
            table.Columns.Add("StudentID", Type.GetType("System.Int32"));
            table.Columns.Add("FirstName", Type.GetType("System.Int32"));
            table.Columns.Add("LastName", Type.GetType("System.Int32"));
            table.Columns.Add("Date of Birth", Type.GetType("System.Int32"));
            table.Columns.Add("Age", Type.GetType("System.Int32"));
            table.Columns.Add("Gender", Type.GetType("System.Int32"));
            table.Columns.Add("Address", Type.GetType("System.Int32"));
            table.Columns.Add("Mobile NO", Type.GetType("System.Int32"));
            dataGridView1.DataSource = table;


            MessageBox.Show("Record Inserted");
        }

        private void dataGridView1_CellContentClick(object sender, DataGridViewCellEventArgs e)
        {
            int index;
            index = e.RowIndex;
            DataGridViewRow row = dataGridView1.Rows[index];
            textBox1.Text = row.Cells[0].Value.ToString();
            textBox2.Text = row.Cells[1].Value.ToString();
            textBox3.Text = row.Cells[2].Value.ToString();
            StextBox4.Text = row.Cells[3].Value.ToString();
            textBox5.Text = row.Cells[4].Value.ToString();
            textBox6.Text = row.Cells[5].Value.ToString();
            textBox7.Text = row.Cells[6].Value.ToString();
            textBox8.Text = row.Cells[7].Value.ToString();

        }

        private void button2_Click(object sender, EventArgs e)
        {

            table.Rows.Add(textBox1.Text);



            MessageBox.Show("Record Inserted");
        }

        private void button4_Click(object sender, EventArgs e)
        {
            index = dataGridView1.CurrentCell.RowIndex;
            dataGridView1.Rows.RemoveAt(index);
            MessageBox.Show("Item Removed");
        }

        private void button6_Click(object sender, EventArgs e)
        {
            DataGridViewRow newData = dataGridView1.Rows[index];
            newData.Cells[0].Value = textBox1.Text;
            newData.Cells[1].Value = textBox2.Text;
            newData.Cells[2].Value = textBox3.Text;
            newData.Cells[3].Value = textBox4.Text;
            newData.Cells[4].Value = textBox5.Text;
            newData.Cells[5].Value = textBox6.Text;
            newData.Cells[6].Value = textBox7.Text;
            newData.Cells[7].Value = textBox8.Text;
            MessageBox.Show("Record Updated");
        }

        private void button5_Click(object sender, EventArgs e)
        {
            int SearchID;
            SearchID=int.Parse(textBox1.Text);
            if (SearchID == 1)
            {
                textBox2.Text = "Lady Mary";
                textBox3.Text = "Kahit ano";
                textBox4.Text = "10-29-20";
                textBox5.Text = "2";
                textBox6.Text = "Female";
                textBox7.Text = "Nueva Ecija";
                textBox8.Text = "09553322143";

            }
            else
             {
                textBox2.Text = ("No Record");
                textBox3.Text = ("No Record");
                textBox4.Text = ("No Record");
                textBox5.Text = ("No Record");
                textBox6.Text = ("No Record");
                textBox7.Text = ("No Record");
                textBox8.Text = ("No Record");

            }


           



    }
    }
}
