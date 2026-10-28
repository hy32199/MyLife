Add.js

import React from 'react';
import {
  SafeAreaView,
  ScrollView,
  Text,
  View,
  StyleSheet,
  StatusBar,
} from 'react-native';

const features = [
  { icon: '💰', title: 'Money', color: '#E3F8EC' },
  { icon: '🗓️', title: 'My Day', color: '#E5EDFF' },
  { icon: '🎯', title: 'Goals', color: '#FFF0D9' },
  { icon: '📝', title: 'Notes', color: '#F3E5FF' },
];

export default function App() {
  return (
    <SafeAreaView style={styles.container}>
      <StatusBar barStyle="dark-content" />
      <ScrollView contentContainerStyle={styles.content}>
        <Text style={styles.greeting}>Hello 👋</Text>
        <Text style={styles.heading}>MyLife</Text>
        <Text style={styles.subtitle}>
          Your life, organized in one place.
        </Text>

        <View style={styles.banner}>
          <Text style={styles.bannerTitle}>
            ✨ Small steps, big results
          </Text>
          <Text style={styles.bannerText}>
            Every day is a new chance to grow.
          </Text>
        </View>

        <Text style={styles.sectionTitle}>Your Space</Text>
        <View style={styles.grid}>
          {features.map((item) => (
            <View
              key={item.title}
              style={[styles.card, { backgroundColor: item.color }]}
            >
              <Text style={styles.icon}>{item.icon}</Text>
              <Text style={styles.cardTitle}>{item.title}</Text>
            </View>
          ))}
        </View>

        <View style={styles.today}>
          <Text style={styles.sectionTitle}>Today's Focus 🌱</Text>
          <Text style={styles.task}>☐ Learn something new</Text>
          <Text style={styles.task}>☐ Take care of yourself</Text>
          <Text style={styles.task}>☐ Work toward your goal</Text>
        </View>

        <Text style={styles.footer}>MyLife • Your personal space</Text>
      </ScrollView>
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  container: { flex: 1, backgroundColor: '#F7F8FC' },
  content: { padding: 20, paddingBottom: 40 },
  greeting: { fontSize: 15, color: '#65708A', marginTop: 20 },
  heading: { fontSize: 34, fontWeight: '800', color: '#24345A', marginTop: 6 },
  subtitle: { fontSize: 14, color: '#65708A', marginTop: 5 },
  banner: {
    backgroundColor: '#334FC4',
    borderRadius: 20,
    padding: 20,
    marginTop: 24,
    marginBottom: 28,
  },
  bannerTitle: { fontSize: 19, fontWeight: '700', color: '#FFFFFF' },
  bannerText: { fontSize: 14, color: '#E7ECFF', marginTop: 8 },
  sectionTitle: {
    fontSize: 19,
    fontWeight: '700',
    color: '#24345A',
    marginBottom: 14,
  },
  grid: { flexDirection: 'row', flexWrap: 'wrap', gap: 12 },
  card: {
    width: '47%',
    flexGrow: 1,
    borderRadius: 18,
    padding: 18,
    minHeight: 110,
  },
  icon: { fontSize: 28, marginBottom: 12 },
  cardTitle: { fontSize: 17, fontWeight: '700', color: '#24345A' },
  today: {
    backgroundColor: '#FFFFFF',
    borderRadius: 18,
    padding: 18,
    marginTop: 24,
  },
  task: { fontSize: 14, color: '#46516A', marginBottom: 14 },
  footer: {
    textAlign: 'center',
    color: '#8992A6',
    fontSize: 12,
    marginTop: 28,
  },
});
