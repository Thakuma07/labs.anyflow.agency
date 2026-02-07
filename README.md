# 🍂 Fall — Advanced Scroll Animation with GSAP & Lenis

A premium, performance-optimized scroll animation experience built with **Next.js**, **GSAP**, and **Lenis**. This project features a unique "falling debris" effect where text components dynamically shed architectural layers as they enter the viewport.

![Project Preview](https://github.com/user-attachments/assets/da2b1b3a-8606-4ec9-b8ac-e71e192c4e21) <!-- Placeholder for actual preview if available -->

## ✨ Key Features

- **Dynamic Typography Interaction**: Leveraging GSAP `SplitText` to orchestrate per-word animations.
- **Architectural Falling Effect**: Custom logic that generates physical "color boxes" over text elements, which react to scroll triggers by falling away with staggered physics.
- **Ultra-Smooth Scrolling**: Integrated **Lenis** for a refined, high-end feel that enhances the GSAP animation timing.
- **Responsive Layout**: Built with **Tailwind CSS**, ensuring the cinematic experience translates across all screen sizes.
- **Modular Component Design**: Easily reusable `<Fall />` component for any text-based animation.

---

## 🛠️ Built With

- **[Next.js 15+](https://nextjs.org/)** - Modern React Framework for the web.
- **[GSAP (GreenSock)](https://gsap.com/)** - The industry standard for high-performance animations.
- **[ScrollTrigger](https://gsap.com/docs/v3/Plugins/ScrollTrigger/)** - GSAP plugin for scroll-based motion.
- **[SplitText](https://gsap.com/docs/v3/Plugins/SplitText/)** - GSAP premium plugin for text manipulation.
- **[Lenis](https://lenis.darkroom.engineering/)** - Smooth scrolling library for a cohesive UX.
- **[Tailwind CSS](https://tailwindcss.com/)** - Utility-first CSS framework.

---

## 🚀 Getting Started

### Prerequisites

- Node.js (Latest LTS recommended)
- npm / pnpm / yarn / bun

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/fall.git
   cd fall
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Run the development server:**
   ```bash
   npm run dev
   ```

Open [http://localhost:3000](http://localhost:3000) to see the result.

---

## 🧠 How It Works

### The `<Fall />` Component
The core of this project resides in `src/components/Fall.jsx`. This component performs the following operations:

1. **Text Splitting**: Uses `SplitText` to break children elements into individual words.
2. **Dynamic Overlay Injection**: For every word, a relative `div` (color box) is injected into the DOM.
3. **GSAP Timeline**:
   - **Trigger**: Activates when the element enters 80% of the viewport.
   - **Physics**: Boxes are animated using `y`, `x`, and `rotation` with random values to simulate natural falling.
   - **Cleanup**: Injected boxes are set to `display: none` upon completion to prevent DOM bloat and layout issues.

### Smooth Scroll Integration
`src/components/SmoothScroll/Lenis.jsx` syncs the Lenis instance with the GSAP ticker, ensuring that all ScrollTrigger calculations are perfectly aligned with the frame rate of the smooth scroll.

---

## 📖 Usage

To use the falling effect in your pages:

```jsx
import Fall from '@/components/Fall';

export default function MySection() {
  return (
    <section>
      <Fall color="#3498db" delay={0.5}>
        <h1>This text will shed its blue skin on scroll.</h1>
      </Fall>
    </section>
  );
}
```

### Component Props
| Prop | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `children` | `node` | *Required* | The text element to animate. |
| `delay` | `number` | `0` | Delay before the animation starts. |
| `color` | `string` | `#ededed` | The hex/rgb color of the falling boxes. |

---

## 📂 Project Structure

```text
├── public/          # Assets and static files
├── src/
│   ├── app/         # Next.js App Router (Layouts & Pages)
│   ├── components/  # Core animation components
│   │   ├── Fall.jsx # The engine behind the falling effect
│   │   ├── SmoothScroll/ # Lenis implementation
│   │   └── Structure.jsx # Example layout implementation
│   └── fonts/       # Project typography
└── tailwind.config  # Design tokens and theme settings
```

---

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<p align="center">Made with ❤️ for cinematic web experiences.</p>
