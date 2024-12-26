namespace FitnessClub
{
    public partial class FrameAuthorization : Form
    {
        public FrameAuthorization()
        {
            InitializeComponent();
        }

        bool action = false;
        private void ChooseRegistrationButton_Click(object sender, EventArgs e)
        {
            this.Hide();
            new FrameRegistration().Show();
        }

        private void RegisterButton_Click(object sender, EventArgs e)
        {
            if (FieldLoginPart2.Text.Length >= 4 & FieldPasswordPart2.Text.Length >= 8 & FieldLoginPart2.Text != FieldPasswordPart2.Text & FieldPhoneNumberPart2.Text.Length >= 17)
            {
                this.Hide();
                MessageBox.Show("Вы вошли в свой аккаунт");
                new FramePersonalWeb().Show();
            }
            else if (FieldLoginPart2.Text == "Admin")
            {
                this.Hide();
                MessageBox.Show("Вы вошли в свой аккаунт");
                new FramePersonalWeb().Show();
            }
            else if (FieldLoginPart2.Text.Length == 0 & FieldPhoneNumberPart2.Text.Length < 17 & FieldPhoneNumberPart2.Text.Length != 17)
            {
                MessageBox.Show("Вы не ввели номер телефона");
            }
            else if (FieldLoginPart2.Text.Length == 0 & FieldPasswordPart2.Text.Length >= 8 & FieldPhoneNumberPart2.Text.Length >= 17)
            {
                this.Hide();
                MessageBox.Show("Вы вошли в свой аккаунт по номеру телефона");
                new FramePersonalWeb().Show();
            }
            else
            {
                MessageBox.Show("Неверный логин или пароль!");
            }
        }

        private void closeAuthorize_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void FieldLoginPart2_KeyPress(object sender, KeyPressEventArgs e)
        {
            char number = e.KeyChar;

            if (!Char.IsDigit(number) & number != 8 & !((e.KeyChar >= 'a' && e.KeyChar <= 'z')) & !((e.KeyChar >= 'A' && e.KeyChar <= 'Z')) & number != 95)
            {
                e.Handled = true;
            }
        }

        private void FieldPasswordPart2_KeyPress(object sender, KeyPressEventArgs e)
        {
            char number = e.KeyChar;

            if (!Char.IsDigit(number) & number != 8 & !((e.KeyChar >= 'a' && e.KeyChar <= 'z')) & !((e.KeyChar >= 'A' && e.KeyChar <= 'Z')) & !((e.KeyChar >= 33 && e.KeyChar <= 47)) & !((e.KeyChar >= 58 && e.KeyChar <= 64)) & !((e.KeyChar >= 91 && e.KeyChar <= 96)) & !((e.KeyChar >= 123 && e.KeyChar <= 126)))
            {
                e.Handled = true;
            }

        }

        private void HidenPassword2_Click(object sender, EventArgs e)
        {
            if (!action)
            {
                FieldPasswordPart2.UseSystemPasswordChar = false;
                action = true;
            }
            else
            {
                FieldPasswordPart2.UseSystemPasswordChar = true;
                action = false;
            }
        }

        private void FieldPasswordPart2_TextChanged(object sender, EventArgs e)
        {
            if (!action)
            {
                FieldPasswordPart2.UseSystemPasswordChar = true;
            }
        }
    }
}

namespace FitnessClub
{
    public partial class FrameChooseTimeToTrain : Form
    {
        public FrameChooseTimeToTrain()
        {
            InitializeComponent();
        }

        private void closeTimeSet_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void Back1_Click(object sender, EventArgs e)
        {
            this.Hide();
            new FrameMainFrame().Show();
        }

        private void DateAndTimeButton_KeyPress(object sender, KeyPressEventArgs e)
        {
            char number = e.KeyChar;

            if (!Char.IsDigit(number) & number != 8 & number != 46 & number != 124 & number != 58)
            {
                e.Handled = true;
            }
        }

        private void AgreeButton_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET TimeStartTask = '{DateAndTimeButton.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.timer = DateAndTimeButton.Text;
            this.Hide();
            MessageBox.Show($"Ваше время: {DateAndTimeButton.Text}");
            new FramePersonalWeb().Show();
        }

        private void Close9_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }
    }
}

namespace FitnessClub
{
    public partial class FrameChooseTrainerMan : Form
    {
        public FrameChooseTrainerMan()
        {
            InitializeComponent();
        }

        private void B4Wom_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTrainer = '{tr3Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET TrainerName = '{tr3Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.trainer = tr3Man.Text;
            DataSend.image = "m3";
            this.Hide();
            new FrameChooseTimeToTrain().Show();
        }

        private void Tr2Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTrainer = '{tr2Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET TrainerName = '{tr2Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.trainer = tr2Man.Text;
            DataSend.image = "m2";
            this.Hide();
            new FrameChooseTimeToTrain().Show();
        }

        private void Tr4Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTrainer = '{tr4Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET TrainerName = '{tr4Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.trainer = tr4Man.Text;
            DataSend.image = "m4";
            this.Hide();
            new FrameChooseTimeToTrain().Show();
        }

        private void Tr1Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTrainer = '{tr1Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET TrainerName = '{tr1Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.trainer = tr1Man.Text;
            DataSend.image = "m1";
            this.Hide();
            new FrameChooseTimeToTrain().Show();
        }

        private void Back2_Click(object sender, EventArgs e)
        {
            this.Hide();
            new FrameMenuMan().Show();
        }

        private void closeTrainMan_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void Close8_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        bool titleOpen5 = false;
        bool titleOpen6 = false;
        bool titleOpen7 = false;
        bool titleOpen8 = false;

        private void InfoButton5_Click(object sender, EventArgs e)
        {
            if (!titleOpen5)
            {
                InfoTitle5.Show();
                titleOpen5 = true;
            }
            else
            {
                InfoTitle5.Hide();
                titleOpen5 = false;
            }
        }

        private void InfoButton6_Click(object sender, EventArgs e)
        {
            if (!titleOpen6)
            {
                InfoTitle6.Show();
                titleOpen6 = true;
            }
            else
            {
                InfoTitle6.Hide();
                titleOpen6 = false;
            }
        }

        private void InfoButton7_Click(object sender, EventArgs e)
        {
            if (!titleOpen7)
            {
                InfoTitle7.Show();
                titleOpen7 = true;
            }
            else
            {
                InfoTitle7.Hide();
                titleOpen7 = false;
            }
        }

        private void InfoButton8_Click(object sender, EventArgs e)
        {
            if (!titleOpen8)
            {
                InfoTitle8.Show();
                titleOpen8 = true;
            }
            else
            {
                InfoTitle8.Hide();
                titleOpen8 = false;
            }
        }
    }
}

namespace FitnessClub
{
    public partial class FrameChooseTrainerWoman : Form
    {
        public FrameChooseTrainerWoman()
        {
            InitializeComponent();
        }

        private void Tr4Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTrainer = '{tr4Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET TrainerName = '{tr4Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.trainer = tr4Man.Text;
            DataSend.image = "w4";
            this.Hide();
            new FrameChooseTimeToTrain().Show();
        }

        private void Tr2Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTrainer = '{tr2Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET TrainerName = '{tr2Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.trainer = tr2Man.Text;
            DataSend.image = "w2";
            this.Hide();
            new FrameChooseTimeToTrain().Show();
        }

        private void Tr1Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTrainer = '{tr1Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET TrainerName = '{tr1Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.trainer = tr1Man.Text;
            DataSend.image = "w1";
            this.Hide();
            new FrameChooseTimeToTrain().Show();
        }

        private void Tr3Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTrainer = '{tr3Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET TrainerName = '{tr3Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.trainer = tr3Man.Text;
            DataSend.image = "w3";
            this.Hide();
            new FrameChooseTimeToTrain().Show();
        }

        private void Back2_Click(object sender, EventArgs e)
        {
            this.Hide();
            new FrameMenuWoman().Show();
        }

        private void closeTrainWoman_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void closeAuthorize_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        bool titleOpen1 = false;
        bool titleOpen2 = false;
        bool titleOpen3 = false;
        bool titleOpen4 = false;

        private void InfoButton1_Click(object sender, EventArgs e)
        {
            if (!titleOpen1)
            {
                InfoTitle1.Show();
                titleOpen1 = true;
            }
            else
            {
                InfoTitle1.Hide();
                titleOpen1 = false;
            }
        }

        private void InfoButton2_Click(object sender, EventArgs e)
        {
            if (!titleOpen2)
            {
                InfoTitle2.Show();
                titleOpen2 = true;
            }
            else
            {
                InfoTitle2.Hide();
                titleOpen2 = false;
            }
        }

        private void InfoButton3_Click(object sender, EventArgs e)
        {
            if (!titleOpen3)
            {
                InfoTitle3.Show();
                titleOpen3 = true;
            }
            else
            {
                InfoTitle3.Hide();
                titleOpen3 = false;
            }
        }

        private void InfoButton4_Click(object sender, EventArgs e)
        {
            if (!titleOpen4)
            {
                InfoTitle4.Show();
                titleOpen4 = true;
            }
            else
            {
                InfoTitle4.Hide();
                titleOpen4 = false;
            }
        }
    }
}

namespace FitnessClub
{
    public partial class FrameMainFrame : Form
    {
        public FrameMainFrame()
        {
            InitializeComponent();
        }
        private void ChooseSexualMan_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserClients SET Sexual = '{ChooseSexualMan.Text}' WHERE UserName = '{DataSend.name}' ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.sexual = ChooseSexualMan.Text;
            this.Hide();
            new FrameMenuMan().Show();
        }

        private void ChooseSexualWoman_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserClients SET Sexual = '{ChooseSexualWoman.Text}' WHERE UserName = '{DataSend.name}' ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.sexual = ChooseSexualWoman.Text;
            this.Hide();
            new FrameMenuWoman().Show();
        }

        private void closeSexual_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void Close6_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }
    }
}

namespace FitnessClub
{
    public partial class FrameMenuMan : Form
    {
        int price1 = 800;
        int price2 = 1250;
        int price3 = 550;
        int price4 = 700;
        int price5 = 1750;
        int price6 = 850;
        public FrameMenuMan()
        {
            InitializeComponent();
        }

        private void b5Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b5Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price5}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b5Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.task = b5Man.Text;
            DataSend.price = price5;
            this.Hide();
            new FrameChooseTrainerMan().Show();
        }

        private void b6Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b6Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price6}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b6Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.task = b6Man.Text;
            DataSend.price = price6;
            this.Hide();
            new FrameChooseTrainerMan().Show();
        }

        private void b4Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b4Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price4}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b4Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.task = b4Man.Text;
            DataSend.price = price4;
            this.Hide();
            new FrameChooseTrainerMan().Show();
        }

        private void b3Man_Click(object sender, EventArgs e)
        {
            SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            bd.Open();
            SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b3Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price3}' WHERE UserName = '{DataSend.name}', ", bd);
            SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b3Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            command.ExecuteNonQuery();
            bd.Close();
            DataSend.task = b3Man.Text;
            DataSend.price = price3;
            this.Hide();
            new FrameChooseTrainerMan().Show();
        }

        private void b2Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b2Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price2}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b2Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.task = b2Man.Text;
            DataSend.price = price2;
            this.Hide();
            new FrameChooseTrainerMan().Show();
        }

        private void b1Man_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b1Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price1}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b1Man.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.task = b1Man.Text;
            DataSend.price = price1;
            this.Hide();
            new FrameChooseTrainerMan().Show();
        }

        private void Back1_Click(object sender, EventArgs e)
        {
            this.Hide();
            new FrameMainFrame().Show();
        }

        private void closeTaskMan_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void Close5_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }
    }
}

namespace FitnessClub
{
    public partial class FrameMenuWoman : Form
    {
        int price1 = 1000;
        int price2 = 750;
        int price3 = 500;
        int price4 = 850;
        int price5 = 1250;
        int price6 = 2250;
        public FrameMenuWoman()
        {
            InitializeComponent();
        }

        private void B1Wom_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b1Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price1}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b1Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.task = b1Wom.Text;
            DataSend.price = price1;
            this.Hide();
            new FrameChooseTrainerWoman().Show();
        }

        private void B5Wom_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b5Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price5}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b5Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.task = b5Wom.Text;
            DataSend.price = price5;
            this.Hide();
            new FrameChooseTrainerWoman().Show();
        }

        private void B4Wom_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b4Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price4}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b4Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.task = b4Wom.Text;
            DataSend.price = price4;
            this.Hide();
            new FrameChooseTrainerWoman().Show();
        }

        private void B3Wom_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b3Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price3}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b3Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.task = b3Wom.Text;
            DataSend.price = price3;
            this.Hide();
            new FrameChooseTrainerWoman().Show();
        }

        private void B2Wom_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b2Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price2}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b2Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.task = b2Wom.Text;
            DataSend.price = price2;
            this.Hide();
            new FrameChooseTrainerWoman().Show();
        }

        private void B6Wom_Click(object sender, EventArgs e)
        {
            //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
            //bd.Open();
            //SqlCommand command = new SqlCommand($"UPDATE UserTasks SET NameTask = '{b6Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command2 = new SqlCommand($"UPDATE UserTasks SET CostTask = '{price6}' WHERE UserName = '{DataSend.name}', ", bd);
            //SqlCommand command3 = new SqlCommand($"UPDATE Trainers SET Task = '{b6Wom.Text}' WHERE UserName = '{DataSend.name}', ", bd);
            //command.ExecuteNonQuery();
            //bd.Close();
            DataSend.task = b6Wom.Text;
            DataSend.price = price6;
            this.Hide();
            new FrameChooseTrainerWoman().Show();
        }

        private void Back2_Click(object sender, EventArgs e)
        {
            this.Hide();
            new FrameMainFrame().Show();
        }

        private void closeTaskWoman_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void Close4_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }
    }
}

namespace FitnessClub
{
    public partial class FramePersonalWeb : Form
    {
        public FramePersonalWeb()
        {
            InitializeComponent();
            this.labelName.Text = DataSend.name;
            this.labelPhoneNumber.Text = DataSend.phone;
            this.labelSexual.Text = DataSend.sexual;
        }

        private void ChooseWeb_Click(object sender, EventArgs e)
        {
            if (Task1.Text == "1.Занято" & Task2.Text == "2.Занято" & Task3.Text == "3.Занято")
            {
                MessageBox.Show("У вас нет свободных записей!");
            }
            else
            {
                this.Hide();
                new FrameMainFrame().Visible = true;
            }
        }

        private void Button1_Click(object sender, EventArgs e)
        {
            if (TaskChoose.Text == "1")
            {
                Task1.Text = "1.";
                TaskChoose.Text = "";
                MessageBox.Show("Вы отменили 1 запись");
            }
            else if (TaskChoose.Text == "2")
            {
                Task2.Text = "2.";
                TaskChoose.Text = "";
                MessageBox.Show("Вы отменили 2 запись");
            }
            else if (TaskChoose.Text == "3")
            {
                Task3.Text = "3.";
                TaskChoose.Text = "";
                MessageBox.Show("Вы отменили 3 запись");
            }
            else if (TaskChoose.Text == "1.")
            {
                Task2.Text = "1.";
                TaskChoose.Text = "";
                MessageBox.Show("Вы отменили 1 запись");
            }
            else if (TaskChoose.Text == "2.")
            {
                Task2.Text = "2.";
                TaskChoose.Text = "";
                MessageBox.Show("Вы отменили 2 запись");
            }
            else if (TaskChoose.Text == "3.")
            {
                Task3.Text = "3.";
                TaskChoose.Text = "";
                MessageBox.Show("Вы отменили 3 запись");
            }
            else
            {
                MessageBox.Show("Вы не ввели запись!");
            }
        }

        private void closePersonalWeb_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void closeAuthorize_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void TaskChoose_KeyPress(object sender, KeyPressEventArgs e)
        {
            char number = e.KeyChar;

            if (number != 8 & number != 49 & number != 50 & number != 51)
            {
                e.Handled = true;
            }
        }

        private void Task1_Click(object sender, EventArgs e)
        {
            InfoTask1Screen info = new InfoTask1Screen();
            info.ShowDialog();
        }

        private void Task2_Click(object sender, EventArgs e)
        {
            InfoTask2Screen info = new InfoTask2Screen();
            info.ShowDialog();
        }

        private void Task3_Click(object sender, EventArgs e)
        {
            InfoTask3Screen info = new InfoTask3Screen();
            info.ShowDialog();
        }

        //private void labelName_Click(object sender, EventArgs e)
        //{
        //    SqlConnection bd = new SqlConnection(@"Data Source=510-13;Initial Catalog=FitnessClub;Integrated Security=True");
        //    string Sql = $"select UserName from [dbo].[UserClients] where UserName = '{DataSend.name}'";
        //    SqlCommand cmd = new SqlCommand(Sql, bd);
        //    bd.Open();
        //    SqlDataReader reader = cmd.ExecuteReader();
        //    while (reader.Read())
        //    {
        //        string name = reader["UserName"].ToString();
        //        labelName.Text = name;
        //    }
        //    bd.Close();
        //}
    }
}

namespace FitnessClub
{
    public partial class FrameRegistration : Form
    {
        public FrameRegistration()
        {
            InitializeComponent();
        }

        bool action = false;
        private void ChooseAuthorizeButton_Click(object sender, EventArgs e)
        {
            this.Hide();
            new FrameAuthorization().Show();
        }

        private void RegisterButton_Click(object sender, EventArgs e)
        {
            if (FieldLoginPart1.Text.Length >= 5 & FieldPasswordPart1.Text.Length >= 8 & FieldLoginPart1.Text != FieldPasswordPart1.Text & FieldPhoneNumberPart1.Text.Length >= 17)
            {
                //SqlConnection bd = new SqlConnection(@"Data Source=510-06;Initial Catalog=FitnessClub;Integrated Security=True");
                //bd.Open();
                //SqlCommand command = new SqlCommand("INSERT INTO [dbo].[UserClients] (UserName, UserPassword, PhoneNumber) VALUES (@UserName, @UserPassword, @PhoneNumber)", bd);
                //command.Parameters.Add("@UserName", SqlDbType.VarChar).Value = FieldLoginPart1.Text;
                //command.Parameters.Add("@UserPassword", SqlDbType.VarChar).Value = FieldPasswordPart1.Text;
                //command.Parameters.Add("@PhoneNumber", SqlDbType.VarChar).Value = FieldPhoneNumberPart1.Text;
                //command.ExecuteNonQuery();

                //SqlCommand command2 = new SqlCommand("INSERT INTO [dbo].[UserTasks] (UserName, UserPhoneNumber) VALUES (@UserName, @UserPhoneNumber)", bd);
                //command2.Parameters.Add("@UserName", SqlDbType.VarChar).Value = FieldLoginPart1.Text;
                //command2.Parameters.Add("@UserPhoneNumber", SqlDbType.VarChar).Value = FieldPhoneNumberPart1.Text;
                //command2.ExecuteNonQuery();

                //SqlCommand command3 = new SqlCommand("INSERT INTO [dbo].[Trainers] (UserName, UserPhoneNumber) VALUES (@UserName, @UserPhoneNumber)", bd);
                //command3.Parameters.Add("@UserName", SqlDbType.VarChar).Value = FieldLoginPart1.Text;
                //command3.Parameters.Add("@UserPhoneNumber", SqlDbType.VarChar).Value = FieldPhoneNumberPart1.Text;
                //command3.ExecuteNonQuery();
                //bd.Close();
                DataSend.name = FieldLoginPart1.Text;
                DataSend.phone = FieldPhoneNumberPart1.Text;
                this.Hide();
                MessageBox.Show("Вы зарегистрировались");
                new FrameMainFrame().Show();
            }
            else if (FieldLoginPart1.Text.Length < 5)
            {
                MessageBox.Show("Вы ввели слишком короткий логин");
            }
            else if (FieldLoginPart1.Text.Length > 12)
            {
                MessageBox.Show("Вы ввели слишком длинный логин");
            }
            else if (FieldPasswordPart1.Text.Length < 8)
            {
                MessageBox.Show("Вы ввели слишком короткий пароль");
            }
            else if (FieldPasswordPart1.Text.Length > 16)
            {
                MessageBox.Show("Вы ввели слишком длинный пароль");
            }
            else if (FieldPhoneNumberPart1.Text.Length < 17 & FieldPhoneNumberPart1.Text.Length != 17)
            {
                MessageBox.Show("Вы не ввели номер телефона");
            }
            else
            {
                MessageBox.Show("Неверная регистрация");
            }
        }

        private void closeRegistration_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void FieldLoginPart1_KeyPress(object sender, KeyPressEventArgs e)
        {
            char number = e.KeyChar;

            if (!Char.IsDigit(number) & number != 8 & !((e.KeyChar >= 'a' && e.KeyChar <= 'z')) & !((e.KeyChar >= 'A' && e.KeyChar <= 'Z')) & number != 95)
            {
                e.Handled = true;
            }
        }

        private void FieldPasswordPart1_KeyPress(object sender, KeyPressEventArgs e)
        {
            char number = e.KeyChar;

            if (!Char.IsDigit(number) & number != 8 & !((e.KeyChar >= 'a' && e.KeyChar <= 'z')) & !((e.KeyChar >= 'A' && e.KeyChar <= 'Z')) & !((e.KeyChar >= 33 && e.KeyChar <= 47)) & !((e.KeyChar >= 58 && e.KeyChar <= 64)) & !((e.KeyChar >= 91 && e.KeyChar <= 96)) & !((e.KeyChar >= 123 && e.KeyChar <= 126)))
            {
                e.Handled = true;
            }

        }

        private void HidenPassword1_Click(object sender, EventArgs e)
        {
            if (!action)
            {
                FieldPasswordPart1.UseSystemPasswordChar = false;
                action = true;
            }
            else
            {
                FieldPasswordPart1.UseSystemPasswordChar = true;
                action = false;
            }
        }

        private void Close2_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void FieldPasswordPart1_TextChanged(object sender, EventArgs e)
        {
            if (!action)
            {
                FieldPasswordPart1.UseSystemPasswordChar = true;
            }
        }
    }
}

namespace FitnessClub
{
    public partial class HelloScreen : Form
    {
        public HelloScreen()
        {
            InitializeComponent();
        }

        private void LeaveTheProgram_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void EnterToProgram_Click(object sender, EventArgs e)
        {
            this.Hide();
            new FrameAuthorization().Show();
        }

        private void RegistrationToProgram_Click(object sender, EventArgs e)
        {
            this.Hide();
            new FrameRegistration().Show();
        }

        private void Close1_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }
    }
}

namespace FitnessClub
{
    public partial class InfoTask1Screen : Form
    {
        public InfoTask1Screen()
        {
            InitializeComponent();

            this.TitleTrainer1.Text = DataSend.trainer;
            this.TitleExercise1.Text = DataSend.task;
            this.TitleCost1.Text = Convert.ToString(DataSend.price);
            this.TitleTimeStart1.Text = Convert.ToString(DataSend.timer);

            FrameChooseTrainerMan manTrainer = new FrameChooseTrainerMan();
            FrameChooseTrainerWoman womanTrainer = new FrameChooseTrainerWoman();

            if (DataSend.image == "m1")
                this.ImageTrainer1.Image = manTrainer.tr1Man.Image;
            else if (DataSend.image == "m2")
                this.ImageTrainer1.Image = manTrainer.tr2Man.Image;
            else if (DataSend.image == "m3")
                this.ImageTrainer1.Image = manTrainer.tr3Man.Image;
            else if (DataSend.image == "m4")
                this.ImageTrainer1.Image = manTrainer.tr4Man.Image;
            else if (DataSend.image == "w1")
                this.ImageTrainer1.Image = womanTrainer.tr1Man.Image;
            else if (DataSend.image == "w2")
                this.ImageTrainer1.Image = manTrainer.tr2Man.Image;
            else if (DataSend.image == "w3")
                this.ImageTrainer1.Image = manTrainer.tr3Man.Image;
            else if (DataSend.image == "w4")
                this.ImageTrainer1.Image = manTrainer.tr4Man.Image;

        }

        private void Close1_Click_1(object sender, EventArgs e)
        {
            this.Hide();
        }
    }
}

namespace FitnessClub
{
    public partial class InfoTask2Screen : Form
    {
        public InfoTask2Screen()
        {
            InitializeComponent();

            this.TitleTrainer2.Text = DataSend.trainer;
            this.TitleExercise2.Text = DataSend.task;
            this.TitleCost2.Text = Convert.ToString(DataSend.price);
            this.TitleTimeStart2.Text = Convert.ToString(DataSend.timer);

            FrameChooseTrainerMan manTrainer = new FrameChooseTrainerMan();
            FrameChooseTrainerWoman womanTrainer = new FrameChooseTrainerWoman();

            if (DataSend.image == "m1")
                this.ImageTrainer2.Image = manTrainer.tr1Man.Image;
            else if (DataSend.image == "m2")
                this.ImageTrainer2.Image = manTrainer.tr2Man.Image;
            else if (DataSend.image == "m3")
                this.ImageTrainer2.Image = manTrainer.tr3Man.Image;
            else if (DataSend.image == "m4")
                this.ImageTrainer2.Image = manTrainer.tr4Man.Image;
            else if (DataSend.image == "w1")
                this.ImageTrainer2.Image = womanTrainer.tr1Man.Image;
            else if (DataSend.image == "w2")
                this.ImageTrainer2.Image = manTrainer.tr2Man.Image;
            else if (DataSend.image == "w3")
                this.ImageTrainer2.Image = manTrainer.tr3Man.Image;
            else if (DataSend.image == "w4")
                this.ImageTrainer2.Image = manTrainer.tr4Man.Image;

        }

        private void Close2_Click_1(object sender, EventArgs e)
        {
            this.Hide();
        }
    }
}

namespace FitnessClub
{
    public partial class InfoTask3Screen : Form
    {
        public InfoTask3Screen()
        {
            InitializeComponent();

            this.TitleTrainer3.Text = DataSend.trainer;
            this.TitleExercise3.Text = DataSend.task;
            this.TitleCost3.Text = Convert.ToString(DataSend.price);
            this.TitleTimeStart3.Text = Convert.ToString(DataSend.timer);

            FrameChooseTrainerMan manTrainer = new FrameChooseTrainerMan();
            FrameChooseTrainerWoman womanTrainer = new FrameChooseTrainerWoman();

            if (DataSend.image == "m1")
                this.ImageTrainer3.Image = manTrainer.tr1Man.Image;
            else if (DataSend.image == "m2")
                this.ImageTrainer3.Image = manTrainer.tr2Man.Image;
            else if (DataSend.image == "m3")
                this.ImageTrainer3.Image = manTrainer.tr3Man.Image;
            else if (DataSend.image == "m4")
                this.ImageTrainer3.Image = manTrainer.tr4Man.Image;
            else if (DataSend.image == "w1")
                this.ImageTrainer3.Image = womanTrainer.tr1Man.Image;
            else if (DataSend.image == "w2")
                this.ImageTrainer3.Image = manTrainer.tr2Man.Image;
            else if (DataSend.image == "w3")
                this.ImageTrainer3.Image = manTrainer.tr3Man.Image;
            else if (DataSend.image == "w4")
                this.ImageTrainer3.Image = manTrainer.tr4Man.Image;

        }

        private void Close3_Click(object sender, EventArgs e)
        {
            this.Hide();
        }
    }
}

namespace FitnessClub
{
    internal class DataSend
    {
        public static string name;
        public static string phone;
        public static string sexual;
        public static string task;
        public static int price;
        public static string trainer;
        public static string timer;
        public static string image;
    }
}

namespace FitnessClub
{
    class bdcon
    {
        static string connectionString = "Server=(510-13)\\510-13\\User;Database=FintessClub;Trusted_Connection=True;";

        // Создание подключения
        SqlConnection connection = new SqlConnection(connectionString);
    }
}

namespace FitnessClub
{
    internal static class Program
    {
        /// <summary>
        /// Главная точка входа для приложения.
        /// </summary>
        [STAThread]
        static void Main()
        {
            Application.EnableVisualStyles();
            Application.SetCompatibleTextRenderingDefault(false);
            Application.Run(new HelloScreen());
        }
    }
}
