import streamlit as st

# Ramashiya Foods - Streamlit single-file website
# Save this file as streamlit_app.py and run: streamlit run streamlit_app.py

st.set_page_config(page_title="Ramashiya Foods", layout="wide", page_icon="🐐")

# ---------- Content provided by user ----------
VISION = "To be a leading agribusiness in South Africa, providing high-quality livestock products while promoting sustainable farming and enriching communities."

MISSION = ("At Ramashiya Foods, we are committed to raising healthy Goats, Cows, Ducks and Chickens using sustainable practices, "
           "delivering premium products to our customers, and fostering growth for our employees, partners, and communities.")

CORE_VALUES = [
    ("Quality", "We strive for the highest standards in livestock care and products."),
    ("Sustainability", "We practice environmentally responsible farming methods."),
    ("Innovation", "We embrace modern farming techniques to maximize efficiency."),
    ("Community", "We contribute to the well-being of local communities."),
    ("Growth", "We nurture growth for our business, employees, and partners."),
    ("Nutritional Integrity", "We never compromise on the quality or healthfulness of our products."),
]

ANIMALS = [
    {
        "title": "Goats",
        "desc": "Healthy goats raised with care — suitable for meat, milk, and breeding programs.",
        "image": "https://images.unsplash.com/photo-1518791841217-8f162f1e1131?auto=format&fit=crop&w=1200&q=60"
    },
    {
        "title": "Sheep",
        "desc": "Fine-quality sheep reared for wool, meat and herd growth.",
        "image": "https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=60"
    },
    {
        "title": "Chickens",
        "desc": "Free-range and well-managed chickens producing premium meat and eggs.",
        "image": "https://images.unsplash.com/photo-1542444459-db6f9f4a4d43?auto=format&fit=crop&w=1200&q=60"
    },
    {
        "title": "Eggs",
        "desc": "Fresh, nutritious eggs sourced from our healthy flocks.",
        "image": "https://images.unsplash.com/photo-1502741126161-b048400d1e8c?auto=format&fit=crop&w=1200&q=60"
    },
]

# Simple logo fallback (the app will look for assets/logo.png first)
LOGO_PATH = "assets/logo.png"
LOGO_FALLBACK = "https://images.unsplash.com/photo-1517841905240-472988babdf9?auto=format&fit=crop&w=600&q=60"

# ---------- Helper UI pieces ----------

def show_header():
    cols = st.columns([1, 4])
    with cols[0]:
        try:
            st.image(LOGO_PATH, width=140)
        except Exception:
            st.image(LOGO_FALLBACK, width=140)
    with cols[1]:
        st.markdown("### Ramashiya Foods")
        st.markdown("#### Sustainable livestock farming • South Africa")


def show_vision_mission_values():
    st.subheader("Our Vision")
    st.info(VISION)

    st.subheader("Our Mission")
    st.write(MISSION)

    st.subheader("Core Values")
    value_cols = st.columns(3)
    for i, (title, desc) in enumerate(CORE_VALUES):
        with value_cols[i % 3]:
            st.markdown(f"**{title}**")
            st.write(desc)


def animal_gallery():
    st.title("Our Animals & Products")
    rows = []
    for a in ANIMALS:
        rows.append((a["title"], a["desc"], a["image"]))

    for i in range(0, len(rows), 2):
        cols = st.columns(2)
        for j in range(2):
            if i + j >= len(rows):
                break
            title, desc, img = rows[i + j]
            with cols[j]:
                st.image(img, caption=title, use_column_width=True)
                st.markdown(f"#### {title}")
                st.write(desc)
                st.markdown("---")


# A lightweight livestock health & feed section using contents from uploaded docs
STARTER_MEDS = [
    ("Oxytetracycline LA", "Long-acting antibiotic — used for respiratory and systemic infections."),
    ("Iver-ject (Ivermectin)", "Anti-parasitic for treatment of external/internal parasites."),
    ("Valbazen", "Broad spectrum dewormer."),
    ("Sulfazine (Coccidiosis)", "Used for coccidiosis intestinal infections in young stock."),
]

FEEDS = [
    "Lucerne / Alfalfa (hay or pellets)",
    "Napier or Brachiaria grass",
    "Sorghum, Maize and Sunflower (for seeds)",
    "Commercial grower and layer mixes (for chickens/eggs)",
]


def health_and_feed():
    st.subheader("Starter medications & remedies")
    for med, purpose in STARTER_MEDS:
        st.write(f"**{med}** — {purpose}")

    st.subheader("Recommended feeds & forage")
    for f in FEEDS:
        st.write(f"- {f}")

    st.caption("Note: This page is informational — consult a qualified veterinarian before treating animals.")


# ---------- Page Layout / Navigation ----------

show_header()

page = st.sidebar.selectbox("Navigate", ["Home", "Animals", "Health & Feed", "Contact"])

if page == "Home":
    st.title("Welcome to Ramashiya Foods")
    st.write("**Mission & Vision**")
    show_vision_mission_values()

    st.markdown("---")
    st.subheader("Quick facts")
    c1, c2, c3 = st.columns(3)
    c1.metric("Established", "2025")
    c2.metric("Primary Species", "Goats, Sheep, Chickens, Eggs")
    c3.metric("Location", "South Africa")

    st.markdown("---")
    st.subheader("What we offer")
    st.write("Livestock for sale, eggs, breeding stock, and consultancy on sustainable animal husbandry. Contact us to learn more.")

elif page == "Animals":
    animal_gallery()

elif page == "Health & Feed":
    health_and_feed()

elif page == "Contact":
    st.subheader("Get in touch")
    left, right = st.columns([2, 3])
    with left:
        st.write("**Head Office**")
        st.write("Ramashiya Foods")
        st.write("Some Farm Road, District, Province, South Africa")
        st.write("Email: info@ramashiyafoods.co.za")
        st.write("Phone: +27 600 000 000")
    with right:
        st.write("**Send us a message**")
        name = st.text_input("Your name")
        email = st.text_input("Email")
        msg = st.text_area("Message")
        if st.button("Send message"):
            # In a real app you'd send/store this; here we just show confirmation
            st.success("Thanks, your message was received — we'll get back to you soon!")

# Footer
st.markdown("---")
st.markdown("<small>© Ramashiya Foods — Sustainable livestock farming | Built with Streamlit</small>", unsafe_allow_html=True)

# Helpful developer notes (visible if user expands the source code)
st.sidebar.markdown("---")
st.sidebar.markdown("**Developer notes**")
st.sidebar.markdown("• Replace assets/logo.png with your PNG logo to show a custom logo.\n• Replace the ANIMALS image URLs with local assets (assets/goat.jpg) or your own hosted images.\n• To deploy: `pip install streamlit` then `streamlit run streamlit_app.py`.\n• To publish: use Streamlit Cloud, Render, or a VPS.")
