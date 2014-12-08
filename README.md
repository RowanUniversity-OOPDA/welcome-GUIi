welcome-GUIi
============
import java.awt.EventQueue;


public class welcome {

	private JFrame frame;
	private final Action action = new SwingAction();
	//private LoginWindow login= new LoginWindow();
	static ticketmachine tm = new ticketmachine();

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					welcome window = new welcome();
					window.frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the application.
	 */
	public welcome() {
		initialize();
	}

	/**
	 * Initialize the contents of the frame.
	 */
	private void initialize() {
		frame = new JFrame();
		frame.setBounds(100, 100, 450, 300);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.getContentPane().setLayout(null);
		
		JLabel lblWelcomeToThe = new JLabel("Welcome to the ticket machine");
		lblWelcomeToThe.setBounds(135, 68, 194, 32);
		frame.getContentPane().add(lblWelcomeToThe);
		
		JButton btnBuyNow = new JButton("buy now");
		btnBuyNow.setAction(action);
		btnBuyNow.setBounds(187, 123, 117, 29);
		frame.getContentPane().add(btnBuyNow);
	}
	private class SwingAction extends AbstractAction {
		public SwingAction() {
			putValue(NAME, "Buy now");
			putValue(SHORT_DESCRIPTION, "Some short description");
		}
		public void actionPerformed(ActionEvent e) {
			login.main(null);
			tm.main(null);
			
		}
	}
}
