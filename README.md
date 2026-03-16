Hanggang Kaibigan ka lng



using Microsoft.VisualBasic.FileIO;
using System.Collections;
using System.Windows.Forms;

namespace StudentRegistrationApplication
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            string[] months = {
                "January","February","March","April",
                "May","June","July","August",
                "September","October","November","December"
            };

            foreach (string buwan in months)
            {
                comboBox1.Items.Add(buwan);
            }

            for (int day = 1; day <= 31; day++)
            {
                comboBox2.Items.Add(day.ToString());
            }
            for (int year = 1990; year <= 2026; year++)
            {
                comboBox3.Items.Add(year.ToString());
            }
            ArrayList Programs = new ArrayList();

            Programs.Add("Bachelor of Science in Computer Science");
            Programs.Add("Bachelor of Science in Information Technology");
            Programs.Add("Bachelor of Science in Information Systems");
            Programs.Add("Bachelor of Science in Computer Engineering");

            foreach (string program in Programs)
            {
                comboBox4.Items.Add(program);
            }
            comboBox2.Text = "-Day-";
            comboBox1.Text = "-Month-";
            comboBox3.Text = "-Year-";
            comboBox4.Text = "-Select program-";
        }

        private void radioButton1_CheckedChanged(object sender, EventArgs e)
        {

        }

        private void button1_Click(object sender, EventArgs e)
        {
            string day = comboBox2.Text;
            string month = comboBox1.Text;
            string year = comboBox3.Text;
            string prugram = comboBox4.Text;

            if (Male.Checked)
            {
                MessageBox.Show("Student Name: " + Lname.Text + ", " + Fname.Text + " " + Mname.Text + "\nGender: Male " + "\nDate of Birth: " + month + " " + day + ", " + year + "\nProgram: " + prugram, "Registration Complete", MessageBoxButtons.YesNo);
            }
            else
            {
                MessageBox.Show("Student Name: " + Lname.Text + ", " + Fname.Text + " " + Mname.Text + "\nGender: Female " + "\nDate of Birth: " + month + " " + day + ", " + year + "\nProgram: " + prugram, "Registration Complete", MessageBoxButtons.YesNo);
            }
        }
    }
}
